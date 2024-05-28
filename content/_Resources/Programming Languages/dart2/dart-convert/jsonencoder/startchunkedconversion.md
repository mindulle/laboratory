[dart:convert](../../dart-convert/dart-convert-library){._links-link}

startChunkedConversion method
=============================

::: {.section .multi-line-signature}
[ChunkedConversionSink](../chunkedconversionsink-class)\<[Object](../../dart-core/object-class)?\>
startChunkedConversion(

1.  [Sink](../../dart-core/sink-class)\<[String](../../dart-core/string-class)\>
    sink

)

::: {.features}
override
:::
:::

Starts a chunked conversion.

The converter works more efficiently if the given `sink` is a
[StringConversionSink](../stringconversionsink-class).

Returns a chunked-conversion sink that accepts at most one object. It is
an error to invoke `add` more than once on the returned sink.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ChunkedConversionSink<Object?> startChunkedConversion(Sink<String> sink) {
  if (sink is _Utf8EncoderSink) {
    return _JsonUtf8EncoderSink(
        sink._sink,
        _toEncodable,
        JsonUtf8Encoder._utf8Encode(indent),
        JsonUtf8Encoder._defaultBufferSize);
  }
  return _JsonEncoderSink(
      sink is StringConversionSink ? sink : StringConversionSink.from(sink),
      _toEncodable,
      indent);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonEncoder/startChunkedConversion.html>
:::
