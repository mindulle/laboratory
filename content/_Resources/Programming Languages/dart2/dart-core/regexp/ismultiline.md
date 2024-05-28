[dart:core](../../dart-core/dart-core-library){._links-link}

isMultiLine property
====================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isMultiLine
:::

Whether this regular expression matches multiple lines.

If the regexp does match multiple lines, the \"\^\" and \"\$\"
characters match the beginning and end of lines. If not, the characters
match the beginning and end of the input.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isMultiLine;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/isMultiLine.html>
:::
