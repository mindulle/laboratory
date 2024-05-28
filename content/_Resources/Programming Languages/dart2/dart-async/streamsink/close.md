[dart:async](../../dart-async/dart-async-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../future-class) close()

::: {.features}
override
:::
:::

Tells the stream sink that no further streams will be added.

This allows the stream sink to complete any remaining work and release
resources that are no longer needed

Returns a future which is completed when the stream sink has shut down.
If cleaning up can fail, the error may be reported in the returned
future, otherwise it completes with `null`.

Returns the same future as [done](done).

The stream sink may close before the [close](close) method is called,
either due to an error or because it is itself providing events to
someone who has stopped listening. In that case, the [done](done) future
is completed first, and the `close` method will return the `done` future
when called.

Unifies [StreamConsumer.close](../streamconsumer/close) and
[EventSink.close](../eventsink/close) which both mark their object as
not expecting any further events.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSink/close.html>
:::
