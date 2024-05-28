[dart:developer](../../dart-developer/dart-developer-library){._links-link}

controlWebServer method
=======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[ServiceProtocolInfo](../serviceprotocolinfo-class)\>
controlWebServer(

1.  {[bool](../../dart-core/bool-class) enable = false,
2.  [bool](../../dart-core/bool-class)? silenceOutput}

)
:::

Control the web server that the service protocol is accessed through.
`enable` is used as a toggle to enable or disable the web server
servicing requests. If `silenceOutput` is provided and is true, the
server will not output information to the console.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<ServiceProtocolInfo> controlWebServer(
    {bool enable = false, bool? silenceOutput}) async {
  // TODO: When NNBD is complete, delete the following line.
  ArgumentError.checkNotNull(enable, 'enable');
  // Port to receive response from service isolate.
  final RawReceivePort receivePort =
      new RawReceivePort(null, 'Service.controlWebServer');
  final Completer<String?> completer = new Completer<String?>();
  receivePort.handler = (String? uriString) => completer.complete(uriString);
  // Request the information from the service isolate.
  _webServerControl(receivePort.sendPort, enable, silenceOutput);
  // Await the response from the service isolate.
  String? uriString = await completer.future;
  Uri? uri = uriString == null ? null : Uri.parse(uriString);
  // Close the port.
  receivePort.close();
  return new ServiceProtocolInfo(uri);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Service/controlWebServer.html>
:::
