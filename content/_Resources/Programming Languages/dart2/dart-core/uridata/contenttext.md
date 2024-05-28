[dart:core](../../dart-core/dart-core-library){._links-link}

contentText property
====================

::: {#getter .section .multi-line-signature}
[String](../string-class) contentText
:::

The content part of the data URI, as its actual representation.

This string may contain percent escapes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get contentText => _text.substring(_separatorIndices.last + 1);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/contentText.html>
:::
