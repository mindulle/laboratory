[dart:io](../../dart-io/dart-io-library){._links-link}

decode method
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) decode(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    encoded

)

::: {.features}
override
:::
:::

Decodes `encoded` data.

The input is decoded as if by `decoder.convert`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String decode(List<int> encoded) => decoder.convert(encoded);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SystemEncoding/decode.html>
:::
