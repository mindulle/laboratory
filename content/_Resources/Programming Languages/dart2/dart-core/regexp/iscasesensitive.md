[dart:core](../../dart-core/dart-core-library){._links-link}

isCaseSensitive property
========================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isCaseSensitive
:::

Whether this regular expression is case sensitive.

If the regular expression is not case sensitive, it will match an input
letter with a pattern letter even if the two letters are different case
versions of the same letter.

``` {.language-dart data-language="dart"}
final str = 'Parse my string';
var regExp = RegExp(r'STRING', caseSensitive: false);
final hasMatch = regExp.hasMatch(str); // Has matches.
print(regExp.isCaseSensitive); // false

regExp = RegExp(r'STRING', caseSensitive: true);
final hasCaseSensitiveMatch = regExp.hasMatch(str); // No matches.
print(regExp.isCaseSensitive); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isCaseSensitive;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/isCaseSensitive.html>
:::
