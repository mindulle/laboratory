[dart:async](../../dart-async/dart-async-library){._links-link}

addStream method
================

::: {.section .multi-line-signature}
[Future](../future-class) addStream(

1.  [Stream](../stream-class)\<S\> stream

)
:::

Consumes the elements of `stream`.

Listens on `stream` and does something for each event.

Returns a future which is completed when the stream is done being added,
and the consumer is ready to accept a new stream. No further calls to
[addStream](addstream) or [close](close) should happen before the
returned future has completed.

The consumer may stop listening to the stream after an error, it may
consume all the errors and only stop at a done event, or it may be
canceled early if the receiver don\'t want any further events.

If the consumer stops listening because of some error preventing it from
continuing, it may report this error in the returned future, otherwise
it will just complete the future with `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future addStream(Stream<S> stream);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamConsumer/addStream.html>
:::
