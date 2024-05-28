[dart:async](../../dart-async/dart-async-library){._links-link}

pipe method
===========

::: {.section .multi-line-signature}
[Future](../future-class) pipe(

1.  [StreamConsumer](../streamconsumer-class)\<T\> streamConsumer

)
:::

Pipes the events of this stream into `streamConsumer`.

All events of this stream are added to `streamConsumer` using
[StreamConsumer.addStream](../streamconsumer/addstream). The
`streamConsumer` is closed when this stream has been successfully added
to it - when the future returned by `addStream` completes without an
error.

Returns a future which completes when this stream has been consumed and
the consumer has been closed.

The returned future completes with the same result as the future
returned by [StreamConsumer.close](../streamconsumer/close). If the call
to [StreamConsumer.addStream](../streamconsumer/addstream) fails in some
way, this method fails in the same way.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future pipe(StreamConsumer<T> streamConsumer) {
  return streamConsumer.addStream(this).then((_) => streamConsumer.close());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/pipe.html>
:::
