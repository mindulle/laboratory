[dart:developer](../../dart-developer/dart-developer-library){._links-link}

ServiceExtensionResponse.result constructor
===========================================

::: {.section .multi-line-signature}
ServiceExtensionResponse.result(

1.  [String](../../dart-core/string-class) result

)
:::

Creates a successful response to a service protocol extension RPC.

Requires `result` to be a JSON object encoded as a string. When forming
the JSON-RPC message `result` will be inlined directly.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ServiceExtensionResponse.result(String result)
    : result = result,
      errorCode = null,
      errorDetail = null {
  // TODO: When NNBD is complete, delete the following line.
  checkNotNullable(result, "result");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/ServiceExtensionResponse/ServiceExtensionResponse.result.html>
:::
