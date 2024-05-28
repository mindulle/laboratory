[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decoder property
================

::: {#getter .section .multi-line-signature}
[JsonDecoder](../jsondecoder-class) decoder

::: {.features}
override
:::
:::

Returns the decoder of `this`, converting from `T` to `S`.

It may be stateful and should not be reused.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
JsonDecoder get decoder {
  if (_reviver == null) return const JsonDecoder();
  return JsonDecoder(_reviver);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonCodec/decoder.html>
:::
