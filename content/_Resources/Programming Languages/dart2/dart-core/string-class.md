[dart:core](../dart-core/dart-core-library){._links-link}

String class
============

A sequence of UTF-16 code units.

Strings are mainly used to represent text. A character may be
represented by multiple code points, each code point consisting of one
or two code units. For example, the Papua New Guinea flag character
requires four code units to represent two code points, but should be
treated like a single character: \"🇵🇬\". Platforms that do not support
the flag character may show the letters \"PG\" instead. If the code
points are swapped, it instead becomes the Guadeloupe flag \"🇬🇵\"
(\"GP\").

A string can be either single or multiline. Single line strings are
written using matching single or double quotes, and multiline strings
are written using triple quotes. The following are all valid Dart
strings:

``` {.language-dart data-language="dart"}
'Single quotes';
"Double quotes";
'Double quotes in "single" quotes';
"Single quotes in 'double' quotes";

'''A
multiline
string''';

"""
Another
multiline
string""";
```

Strings are immutable. Although you cannot change a string, you can
perform an operation on a string which creates a new string:

``` {.language-dart data-language="dart"}
const string = 'Dart is fun';
print(string.substring(0, 4)); // 'Dart'
```

You can use the plus (`+`) operator to concatenate strings:

``` {.language-dart data-language="dart"}
const string = 'Dart ' + 'is ' + 'fun!';
print(string); // 'Dart is fun!'
```

Adjacent string literals are concatenated automatically:

``` {.language-dart data-language="dart"}
const string = 'Dart ' 'is ' 'fun!';
print(string); // 'Dart is fun!'
```

You can use `${}` to interpolate the value of Dart expressions within
strings. The curly braces can be omitted when evaluating identifiers:

``` {.language-dart data-language="dart"}
const string = 'dartlang';
print('$string has ${string.length} letters'); // dartlang has 8 letters
```

A string is represented by a sequence of Unicode UTF-16 code units
accessible through the [codeUnitAt](string/codeunitat) or the
[codeUnits](string/codeunits) members:

``` {.language-dart data-language="dart"}
const string = 'Dart';
final firstCodeUnit = string.codeUnitAt(0);
print(firstCodeUnit); // 68, aka U+0044, the code point for 'D'.
final allCodeUnits = string.codeUnits;
print(allCodeUnits); // [68, 97, 114, 116]
```

A string representation of the individual code units is accessible
through the index operator:

``` {.language-dart data-language="dart"}
const string = 'Dart';
final charAtIndex = string[0];
print(charAtIndex); // 'D'
```

The characters of a string are encoded in UTF-16. Decoding UTF-16, which
combines surrogate pairs, yields Unicode code points. Following a
similar terminology to Go, Dart uses the name \'rune\' for an integer
representing a Unicode code point. Use the [runes](string/runes)
property to get the runes of a string:

``` {.language-dart data-language="dart"}
const string = 'Dart';
final runes = string.runes.toList();
print(runes); // [68, 97, 114, 116]
```

For a character outside the Basic Multilingual Plane (plane 0) that is
composed of a surrogate pair, [runes](string/runes) combines the pair
and returns a single integer. For example, the Unicode character for a
musical G-clef (\'𝄞\') with rune value 0x1D11E consists of a UTF-16
surrogate pair: `0xD834` and `0xDD1E`. Using
[codeUnits](string/codeunits) returns the surrogate pair, and using
`runes` returns their combined value:

``` {.language-dart data-language="dart"}
const clef = '\u{1D11E}';
for (final item in clef.codeUnits) {
  print(item.toRadixString(16));
  // d834
  // dd1e
}
for (final item in clef.runes) {
  print(item.toRadixString(16)); // 1d11e
}
```

The `String` class cannot be extended or implemented. Attempting to do
so yields a compile-time error.

Other resources
---------------

-   [StringBuffer](stringbuffer-class) to efficiently build a string
    incrementally.
-   [RegExp](regexp-class) to work with regular expressions.
-   [Strings and regular
    expressions](https://dart.dev/guides/libraries/library-tour#strings-and-regular-expressions)

Implemented types

:   -   [Comparable](comparable-class)\<[String](string-class)\>
    -   [Pattern](pattern-class)

Constructors
------------

[String.fromCharCode](string/string.fromcharcode)([int](int-class)
charCode)

::: {.constructor-modifier .features}
factory
:::

Allocates a new string containing the specified `charCode`.

[String.fromCharCodes](string/string.fromcharcodes)([Iterable](iterable-class)\<[int](int-class)\>
charCodes, \[[int](int-class) start = 0, [int](int-class)? end\])

::: {.constructor-modifier .features}
factory
:::

Allocates a new string containing the specified `charCodes`.

[String.fromEnvironment](string/string.fromenvironment)([String](string-class)
name, {[String](string-class) defaultValue = \"\"})

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

The string value of the environment declaration `name`.

Properties {#instance-properties}
----------

[codeUnits](string/codeunits) → [List](list-class)\<[int](int-class)\>

::: {.features}
read-only
:::

An unmodifiable list of the UTF-16 code units of this string.

[hashCode](string/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

A hash code derived from the code units of the string.

[isEmpty](string/isempty) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this string is empty.

[isNotEmpty](string/isnotempty) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this string is not empty.

[length](string/length) → [int](int-class)

::: {.features}
read-only
:::

The length of the string.

[runes](string/runes) → [Runes](runes-class)

::: {.features}
read-only
:::

An [Iterable](iterable-class) of Unicode code-points of this string.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[allMatches](pattern/allmatches)([String](string-class) string,
\[[int](int-class) start = 0\]) →
[Iterable](iterable-class)\<[Match](match-class)\>

::: {.features}
inherited
:::

Matches this pattern against the string repeatedly.

[codeUnitAt](string/codeunitat)([int](int-class) index) →
[int](int-class)

Returns the 16-bit UTF-16 code unit at the given `index`.

[compareTo](string/compareto)([String](string-class) other) →
[int](int-class)

::: {.features}
override
:::

Compares this string to `other`.

[contains](string/contains)([Pattern](pattern-class) other,
\[[int](int-class) startIndex = 0\]) → [bool](bool-class)

Whether this string contains a match of `other`.

[endsWith](string/endswith)([String](string-class) other) →
[bool](bool-class)

Whether this string ends with `other`.

[indexOf](string/indexof)([Pattern](pattern-class) pattern,
\[[int](int-class) start = 0\]) → [int](int-class)

Returns the position of the first match of `pattern` in this string,
starting at `start`, inclusive:

[lastIndexOf](string/lastindexof)([Pattern](pattern-class) pattern,
\[[int](int-class)? start\]) → [int](int-class)

The starting position of the last match `pattern` in this string.

[matchAsPrefix](pattern/matchasprefix)([String](string-class) string,
\[[int](int-class) start = 0\]) → [Match](match-class)?

::: {.features}
inherited
:::

Matches this pattern against the start of `string`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[padLeft](string/padleft)([int](int-class) width,
\[[String](string-class) padding = \' \'\]) → [String](string-class)

Pads this string on the left if it is shorter than `width`.

[padRight](string/padright)([int](int-class) width,
\[[String](string-class) padding = \' \'\]) → [String](string-class)

Pads this string on the right if it is shorter than `width`.

[replaceAll](string/replaceall)([Pattern](pattern-class) from,
[String](string-class) replace) → [String](string-class)

Replaces all substrings that match `from` with `replace`.

[replaceAllMapped](string/replaceallmapped)([Pattern](pattern-class)
from, [String](string-class) replace([Match](match-class) match)) →
[String](string-class)

Replace all substrings that match `from` by a computed string.

[replaceFirst](string/replacefirst)([Pattern](pattern-class) from,
[String](string-class) to, \[[int](int-class) startIndex = 0\]) →
[String](string-class)

Creates a new string with the first occurrence of `from` replaced by
`to`.

[replaceFirstMapped](string/replacefirstmapped)([Pattern](pattern-class)
from, [String](string-class) replace([Match](match-class) match),
\[[int](int-class) startIndex = 0\]) → [String](string-class)

Replace the first occurrence of `from` in this string.

[replaceRange](string/replacerange)([int](int-class) start,
[int](int-class)? end, [String](string-class) replacement) →
[String](string-class)

Replaces the substring from `start` to `end` with `replacement`.

[split](string/split)([Pattern](pattern-class) pattern) →
[List](list-class)\<[String](string-class)\>

Splits the string at matches of `pattern` and returns a list of
substrings.

[splitMapJoin](string/splitmapjoin)([Pattern](pattern-class) pattern,
{[String](string-class) onMatch([Match](match-class))?,
[String](string-class) onNonMatch([String](string-class))?}) →
[String](string-class)

Splits the string, converts its parts, and combines them into a new
string.

[startsWith](string/startswith)([Pattern](pattern-class) pattern,
\[[int](int-class) index = 0\]) → [bool](bool-class)

Whether this string starts with a match of `pattern`.

[substring](string/substring)([int](int-class) start,
\[[int](int-class)? end\]) → [String](string-class)

The substring of this string from `start`, inclusive, to `end`,
exclusive.

[toLowerCase](string/tolowercase)() → [String](string-class)

Converts all characters in this string to lower case.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

[toUpperCase](string/touppercase)() → [String](string-class)

Converts all characters in this string to upper case.

[trim](string/trim)() → [String](string-class)

The string without any leading and trailing whitespace.

[trimLeft](string/trimleft)() → [String](string-class)

The string without any leading whitespace.

[trimRight](string/trimright)() → [String](string-class)

The string without any trailing whitespace.

Operators
---------

[operator \*](string/operator_multiply)([int](int-class) times) →
[String](string-class)

Creates a new string by concatenating this string with itself a number
of times.

[operator +](string/operator_plus)([String](string-class) other) →
[String](string-class)

Creates a new string by concatenating this string with `other`.

[operator ==](string/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

Whether `other` is a `String` with the same sequence of code units.

[operator \[\]](string/operator_get)([int](int-class) index) →
[String](string-class)

The character (as a single-code-unit [String](string-class)) at the
given `index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String-class.html>
:::
