[dart:convert](../../dart-convert/dart-convert-library){._links-link}

startChunkedConversion method
=============================

::: {.section .multi-line-signature}
[StringConversionSink](../stringconversionsink-class)
startChunkedConversion(

1.  [Sink](../../dart-core/sink-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>\>
    sink

)

::: {.features}
override
:::
:::

Starts a chunked conversion.

The converter works more efficiently if the given `sink` is a
[ByteConversionSink](../byteconversionsink-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
StringConversionSink startChunkedConversion(Sink<List<int>> sink) {
  return _Utf8EncoderSink(
      sink is ByteConversionSink ? sink : ByteConversionSink.from(sink));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Encoder/startChunkedConversion.html>
:::
