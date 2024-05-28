[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

errors property
===============

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class) errors
:::

Returns a broadcast stream of uncaught errors from the isolate.

Each error is provided as an error event on the stream.

The actual error object and stackTraces will not necessarily be the same
object types as in the actual isolate, but they will always have the
same [Object.toString](../../dart-core/object/tostring) result.

This stream is based on [addErrorListener](adderrorlistener) and
[removeErrorListener](removeerrorlistener).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream get errors {
  StreamController controller = StreamController.broadcast(sync: true);
  RawReceivePort? port;
  void handleError(Object? message) {
    var listMessage = message as List<Object?>;
    var errorDescription = listMessage[0] as String;
    var stackDescription = listMessage[1] as String;
    var error = RemoteError(errorDescription, stackDescription);
    controller.addError(error, error.stackTrace);
  }

  controller.onListen = () {
    RawReceivePort receivePort = RawReceivePort(handleError);
    port = receivePort;
    this.addErrorListener(receivePort.sendPort);
  };
  controller.onCancel = () {
    var listenPort = port!;
    port = null;
    this.removeErrorListener(listenPort.sendPort);
    listenPort.close();
  };
  return controller.stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/errors.html>
:::
