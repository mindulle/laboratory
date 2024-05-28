[dart:io](../../dart-io/dart-io-library){._links-link}

encoder property
================

::: {#getter .section .multi-line-signature}
[Converter](../../dart-convert/converter-class)\<[String](../../dart-core/string-class),
[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>\>
encoder

::: {.features}
override
:::
:::

Returns the encoder from `String` to `List<int>`.

It may be stateful and should not be reused.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Converter<String, List<int>> get encoder {
  if (Platform.operatingSystem == "windows") {
    return const _WindowsCodePageEncoder();
  } else {
    return const Utf8Encoder();
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SystemEncoding/encoder.html>
:::
