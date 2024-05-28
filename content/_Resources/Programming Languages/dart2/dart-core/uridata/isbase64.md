[dart:core](../../dart-core/dart-core-library){._links-link}

isBase64 property
=================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isBase64
:::

Whether the data is Base64 encoded or not.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isBase64 => _separatorIndices.length.isOdd;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/isBase64.html>
:::
