[dart:convert](../../dart-convert/dart-convert-library){._links-link}

indent property
===============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class)? indent

::: {.features}
final
:::
:::

The string used for indention.

When generating multi-line output, this string is inserted once at the
beginning of each indented line for each level of indentation.

If `null`, the output is encoded as a single line.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final String? indent;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonEncoder/indent.html>
:::
