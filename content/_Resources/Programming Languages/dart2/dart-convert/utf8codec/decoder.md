[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decoder property
================

::: {#getter .section .multi-line-signature}
[Utf8Decoder](../utf8decoder-class) decoder

::: {.features}
override
:::
:::

Returns the decoder of `this`, converting from `List<int>` to `String`.

It may be stateful and should not be reused.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Utf8Decoder get decoder {
  // Switch between const objects to avoid allocation.
  return _allowMalformed
      ? const Utf8Decoder(allowMalformed: true)
      : const Utf8Decoder(allowMalformed: false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Codec/decoder.html>
:::
