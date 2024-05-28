[dart:core](../../dart-core/dart-core-library){._links-link}

splitMapJoin method
===================

::: {.section .multi-line-signature}
[String](../string-class) splitMapJoin(

1.  [Pattern](../pattern-class) pattern,
2.  {[String](../string-class) onMatch(
    1.  [Match](../match-class)

    )?,
3.  [String](../string-class) onNonMatch(
    1.  [String](../string-class)

    )?}

)
:::

Splits the string, converts its parts, and combines them into a new
string.

The `pattern` is used to split the string into parts and separating
matches. Each match of [Pattern.allMatches](../pattern/allmatches) of
`pattern` on this string is used as a match, and the substrings between
the end of one match (or the start of the string) and the start of the
next match (or the end of the string) is treated as a non-matched part.
(There is no omission of leading or trailing empty matchs, like in
[split](split), all matches and parts between the are included.)

Each match is converted to a string by calling `onMatch`. If `onMatch`
is omitted, the matched substring is used.

Each non-matched part is converted to a string by a call to
`onNonMatch`. If `onNonMatch` is omitted, the non-matching substring
itself is used.

Then all the converted parts are concatenated into the resulting string.

``` {.language-dart data-language="dart"}
final result = 'Eats shoots leaves'.splitMapJoin(RegExp(r'shoots'),
    onMatch: (m) => '${m[0]}', // (or no onMatch at all)
    onNonMatch: (n) => '*');
print(result); // *shoots*
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String splitMapJoin(Pattern pattern,
    {String Function(Match)? onMatch, String Function(String)? onNonMatch});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/splitMapJoin.html>
:::
