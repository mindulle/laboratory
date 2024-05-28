[dart:io](../../dart-io/dart-io-library){._links-link}

startChunkedConversion method
=============================

::: {.section .multi-line-signature}
[ByteConversionSink](../../dart-convert/byteconversionsink-class)
startChunkedConversion(

1.  [Sink](../../dart-core/sink-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>\>
    sink

)

::: {.features}
override
:::
:::

Start a chunked conversion using the options given to the
[ZLibEncoder](../zlibencoder-class) constructor.

Accepts any `Sink<List<int>>`, but prefers a
[ByteConversionSink](../../dart-convert/byteconversionsink-class), and
converts any other sink to a
[ByteConversionSink](../../dart-convert/byteconversionsink-class) before
using it.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ByteConversionSink startChunkedConversion(Sink<List<int>> sink) {
  if (sink is! ByteConversionSink) {
    sink = new ByteConversionSink.from(sink);
  }
  return new _ZLibEncoderSink._(
      sink, gzip, level, windowBits, memLevel, strategy, dictionary, raw);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibEncoder/startChunkedConversion.html>
:::
