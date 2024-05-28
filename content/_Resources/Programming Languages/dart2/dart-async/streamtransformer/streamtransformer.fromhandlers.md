[dart:async](../../dart-async/dart-async-library){._links-link}

StreamTransformer\<S, T\>.fromHandlers constructor
==================================================

::: {.section .multi-line-signature}
StreamTransformer\<S, T\>.fromHandlers(

1.  {void handleData(
    1.  S data,
    2.  [EventSink](../eventsink-class)\<T\> sink

    )?,
2.  void handleError(
    1.  [Object](../../dart-core/object-class) error,
    2.  [StackTrace](../../dart-core/stacktrace-class) stackTrace,
    3.  [EventSink](../eventsink-class)\<T\> sink

    )?,
3.  void handleDone(
    1.  [EventSink](../eventsink-class)\<T\> sink

    )?}

)
:::

Creates a [StreamTransformer](../streamtransformer-class) that delegates
events to the given functions.

Example use of a duplicating transformer:

``` {.language-dart data-language="dart"}
stringStream.transform(StreamTransformer<String, String>.fromHandlers(
    handleData: (String value, EventSink<String> sink) {
      sink.add(value);
      sink.add(value);  // Duplicate the incoming events.
    }));
```

Transformers that are constructed this way cannot use captured state if
they are used in streams that can be listened to multiple times.

``` {.language-dart data-language="dart"}
StreamController<String> controller = StreamController.broadcast();
controller.onListen = () {
  scheduleMicrotask(() {
    controller.addError("Bad");
    controller.addError("Worse");
    controller.addError("Worst");
  });
};
var sharedState = 0;
var transformedStream = controller.stream.transform(
    StreamTransformer<String>.fromHandlers(
        handleError: (error, stackTrace, sink) {
  sharedState++; // Increment shared error-counter.
  sink.add("Error $sharedState: $error");
}));

transformedStream.listen(print);
transformedStream.listen(print); // Listen twice.
// Listening twice to the same stream makes the transformer share the same
// state. Instead of having "Error 1: Bad", "Error 2: Worse",
// "Error 3: Worst" as output (each twice for the separate subscriptions),
// this program emits:
// Error 1: Bad
// Error 2: Bad
// Error 3: Worse
// Error 4: Worse
// Error 5: Worst
// Error 6: Worst
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StreamTransformer.fromHandlers(
    {void handleData(S data, EventSink<T> sink)?,
    void handleError(Object error, StackTrace stackTrace, EventSink<T> sink)?,
    void handleDone(EventSink<T> sink)?}) = _StreamHandlerTransformer<S, T>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamTransformer/StreamTransformer.fromHandlers.html>
:::
