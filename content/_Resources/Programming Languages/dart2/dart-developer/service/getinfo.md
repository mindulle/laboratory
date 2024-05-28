[dart:developer](../../dart-developer/dart-developer-library){._links-link}

getInfo method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[ServiceProtocolInfo](../serviceprotocolinfo-class)\>
getInfo()
:::

Get information about the service protocol (version number and Uri to
access the service).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<ServiceProtocolInfo> getInfo() async {
  // Port to receive response from service isolate.
  final RawReceivePort receivePort =
      new RawReceivePort(null, 'Service.getInfo');
  final Completer<String?> completer = new Completer<String?>();
  receivePort.handler = (String? uriString) => completer.complete(uriString);
  // Request the information from the service isolate.
  _getServerInfo(receivePort.sendPort);
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
<https://api.dart.dev/stable/2.18.5/dart-developer/Service/getInfo.html>
:::
