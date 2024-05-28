[dart:convert](../../dart-convert/dart-convert-library){._links-link}

startChunkedConversion method
=============================

::: {.section .multi-line-signature}
[ChunkedConversionSink](../chunkedconversionsink-class)\<[Object](../../dart-core/object-class)?\>
startChunkedConversion(

1.  [Sink](../../dart-core/sink-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>\>
    sink

)

::: {.features}
override
:::
:::

Start a chunked conversion.

Only one object can be passed into the returned sink.

The argument `sink` will receive byte lists in sizes depending on the
`bufferSize` passed to the constructor when creating this encoder.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ChunkedConversionSink<Object?> startChunkedConversion(Sink<List<int>> sink) {
  ByteConversionSink byteSink;
  if (sink is ByteConversionSink) {
    byteSink = sink;
  } else {
    byteSink = ByteConversionSink.from(sink);
  }
  return _JsonUtf8EncoderSink(byteSink, _toEncodable, _indent, _bufferSize);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonUtf8Encoder/startChunkedConversion.html>
:::
