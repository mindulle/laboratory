[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.eventTransformed constructor
========================================

::: {.section .multi-line-signature}
Stream\<T\>.eventTransformed(

1.  [Stream](../stream-class) source,
2.  [EventSink](../eventsink-class) mapSink(
    1.  [EventSink](../eventsink-class)\<T\> sink

    )

)
:::

Creates a stream where all events of an existing stream are piped
through a sink-transformation.

The given `mapSink` closure is invoked when the returned stream is
listened to. All events from the `source` are added into the event sink
that is returned from the invocation. The transformation puts all
transformed events into the sink the `mapSink` closure received during
its invocation. Conceptually the `mapSink` creates a transformation pipe
with the input sink being the returned [EventSink](../eventsink-class)
and the output sink being the sink it received.

This constructor is frequently used to build transformers.

Example use for a duplicating transformer:

``` {.language-dart data-language="dart"}
class DuplicationSink implements EventSink<String> {
  final EventSink<String> _outputSink;
  DuplicationSink(this._outputSink);

  void add(String data) {
    _outputSink.add(data);
    _outputSink.add(data);
  }

  void addError(e, [st]) { _outputSink.addError(e, st); }
  void close() { _outputSink.close(); }
}

class DuplicationTransformer extends StreamTransformerBase<String, String> {
  // Some generic types omitted for brevity.
  Stream bind(Stream stream) => Stream<String>.eventTransformed(
      stream,
      (EventSink sink) => DuplicationSink(sink));
}

stringStream.transform(DuplicationTransformer());
```

The resulting stream is a broadcast stream if `source` is.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Stream.eventTransformed(
    Stream<dynamic> source, EventSink<dynamic> mapSink(EventSink<T> sink)) {
  return new _BoundSinkStream(source, mapSink);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.eventTransformed.html>
:::
