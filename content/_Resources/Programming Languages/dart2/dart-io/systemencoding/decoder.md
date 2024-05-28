[dart:io](../../dart-io/dart-io-library){._links-link}

decoder property
================

::: {#getter .section .multi-line-signature}
[Converter](../../dart-convert/converter-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>,
[String](../../dart-core/string-class)\> decoder

::: {.features}
override
:::
:::

Returns the decoder of `this`, converting from `List<int>` to `String`.

It may be stateful and should not be reused.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Converter<List<int>, String> get decoder {
  if (Platform.operatingSystem == "windows") {
    return const _WindowsCodePageDecoder();
  } else {
    return const Utf8Decoder();
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SystemEncoding/decoder.html>
:::
