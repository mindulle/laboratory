[dart:core](../../dart-core/dart-core-library){._links-link}

split method
============

::: {.section .multi-line-signature}
[List](../list-class)\<[String](../string-class)\> split(

1.  [Pattern](../pattern-class) pattern

)
:::

Splits the string at matches of `pattern` and returns a list of
substrings.

Finds all the matches of `pattern` in this string, as by using
[Pattern.allMatches](../pattern/allmatches), and returns the list of the
substrings between the matches, before the first match, and after the
last match.

``` {.language-dart data-language="dart"}
const string = 'Hello world!';
final splitted = string.split(' ');
print(splitted); // [Hello, world!];
```

If the pattern doesn\'t match this string at all, the result is always a
list containing only the original string.

If the `pattern` is a `String`, then it\'s always the case that:

``` {.language-dart data-language="dart"}
string.split(pattern).join(pattern) == string
```

If the first match is an empty match at the start of the string, the
empty substring before it is not included in the result. If the last
match is an empty match at the end of the string, the empty substring
after it is not included in the result. If a match is empty, and it
immediately follows a previous match (it starts at the position where
the previous match ended), then the empty substring between the two
matches is not included in the result.

``` {.language-dart data-language="dart"}
const string = 'abba';
final re = RegExp(r'b*');
// re.allMatches(string) will find four matches:
// * empty match before first "a".
// * match of "bb"
// * empty match after "bb", before second "a"
// * empty match after second "a".
print(string.split(re)); // [a, a]
```

A non-empty match at the start or end of the string, or after another
match, is not treated specially, and will introduce empty substrings in
the result:

``` {.language-dart data-language="dart"}
const string = 'abbaa';
final splitted = string.split('a'); // ['', 'bb', '', '']
```

If this string is the empty string, the result is an empty list if
`pattern` matches the empty string, since the empty string before and
after the first-and-last empty match are not included. (It is still a
list containing the original empty string `[""]` if the pattern doesn\'t
match).

``` {.language-dart data-language="dart"}
const string = '';
print(string.split('')); // []
print(string.split('a')); // []
```

Splitting with an empty pattern splits the string into single-code unit
strings.

``` {.language-dart data-language="dart"}
const string = 'Pub';
print(string.split('')); // [P, u, b]

// Same as:
var codeUnitStrings = [
  for (final unit in string.codeUnits) String.fromCharCode(unit)
];
print(codeUnitStrings); // [P, u, b]
```

Splitting happens at UTF-16 code unit boundaries, and not at rune
(Unicode code point) boundaries:

``` {.language-dart data-language="dart"}
// String made up of two code units, but one rune.
const string = '\u{1D11E}';
final splitted = string.split('');
print(splitted); // ['\ud834', '\udd1e'] - 2 unpaired surrogate values
```

To get a list of strings containing the individual runes of a string,
you should not use split. You can instead get a string for each rune as
follows:

``` {.language-dart data-language="dart"}
const string = '\u{1F642}';
for (final rune in string.runes) {
  print(String.fromCharCode(rune));
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<String> split(Pattern pattern);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/split.html>
:::
