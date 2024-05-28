[dart:convert](../../dart-convert/dart-convert-library){._links-link}

startChunkedConversion method
=============================

::: {.section .multi-line-signature}
[ByteConversionSink](../byteconversionsink-class)
startChunkedConversion(

1.  [Sink](../../dart-core/sink-class)\<[String](../../dart-core/string-class)\>
    sink

)
:::

Starts a chunked conversion.

The converter works more efficiently if the given `sink` is a
[StringConversionSink](../stringconversionsink-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ByteConversionSink startChunkedConversion(Sink<String> sink) {
  StringConversionSink stringSink;
  if (sink is StringConversionSink) {
    stringSink = sink;
  } else {
    stringSink = StringConversionSink.from(sink);
  }
  // TODO(lrn): Use stringSink.asUtf16Sink() if it becomes available.
  if (!_allowInvalid) return _Latin1DecoderSink(stringSink);
  return _Latin1AllowInvalidDecoderSink(stringSink);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Decoder/startChunkedConversion.html>
:::
