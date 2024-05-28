[dart:io](../../dart-io/dart-io-library){._links-link}

IOSink constructor
==================

::: {.section .multi-line-signature}
IOSink(

1.  [StreamConsumer](../../dart-async/streamconsumer-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>\>
    target,
2.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Create an [IOSink](../iosink-class) that outputs to a `target`
[StreamConsumer](../../dart-async/streamconsumer-class) of bytes.

Text written to [StreamSink](../../dart-async/streamsink-class) methods
is encoded to bytes using `encoding` before being output on `target`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory IOSink(StreamConsumer<List<int>> target,
        {Encoding encoding = utf8}) =>
    new _IOSinkImpl(target, encoding);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOSink/IOSink.html>
:::
