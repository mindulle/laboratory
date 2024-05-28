[dart:core](../../dart-core/dart-core-library){._links-link}

source property
===============

::: {.section .multi-line-signature}
dynamic source

::: {.features}
final
:::
:::

The actual source input which caused the error.

This is usually a [String](../string-class), but can be other types too.
If it is a string, parts of it may be included in the
[toString](tostring) message.

The source is `null` if omitted or unknown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final dynamic source;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/FormatException/source.html>
:::
