[dart:developer](../dart-developer/dart-developer-library){._links-link}

ServiceExtensionHandler typedef
===============================

::: {.section .multi-line-signature}
ServiceExtensionHandler =
[Future](../dart-async/future-class)\<[ServiceExtensionResponse](serviceextensionresponse-class)\>
Function([String](../dart-core/string-class) method,
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\> parameters)
:::

A service protocol extension handler. Registered with
[registerExtension](registerextension).

Must complete to a
[ServiceExtensionResponse](serviceextensionresponse-class). `method` is
the method name of the service protocol request, and `parameters` is a
map holding the parameters to the service protocol request.

*NOTE*: all parameter names and values are encoded as strings.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef Future<ServiceExtensionResponse> ServiceExtensionHandler(
    String method, Map<String, String> parameters);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/ServiceExtensionHandler.html>
:::
