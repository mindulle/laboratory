[dart:convert](../../dart-convert/dart-convert-library){._links-link}

encoder property
================

::: {#getter .section .multi-line-signature}
[JsonEncoder](../jsonencoder-class) encoder

::: {.features}
override
:::
:::

Returns the encoder from `S` to `T`.

It may be stateful and should not be reused.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
JsonEncoder get encoder {
  if (_toEncodable == null) return const JsonEncoder();
  return JsonEncoder(_toEncodable);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonCodec/encoder.html>
:::
