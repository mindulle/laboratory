[dart:io](../../dart-io/dart-io-library){._links-link}

text property
=============

::: {.section .multi-line-signature}
[ContentType](../contenttype-class) text

::: {.features}
final
:::
:::

Content type for plain text using UTF-8 encoding.

``` {.language-dart data-language="dart"}
text/plain; charset=utf-8
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static final text = ContentType("text", "plain", charset: "utf-8");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ContentType/text.html>
:::
