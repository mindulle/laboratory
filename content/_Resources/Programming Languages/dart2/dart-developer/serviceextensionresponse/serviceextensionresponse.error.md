[dart:developer](../../dart-developer/dart-developer-library){._links-link}

ServiceExtensionResponse.error constructor
==========================================

::: {.section .multi-line-signature}
ServiceExtensionResponse.error(

1.  [int](../../dart-core/int-class) errorCode,
2.  [String](../../dart-core/string-class) errorDetail

)
:::

Creates an error response to a service protocol extension RPC.

Requires `errorCode` to be [invalidParams](invalidparams-constant) or
between [extensionErrorMin](extensionerrormin-constant) and
[extensionErrorMax](extensionerrormax-constant). Requires `errorDetail`
to be a JSON object encoded as a string. When forming the JSON-RPC
message `errorDetail` will be inlined directly.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ServiceExtensionResponse.error(int errorCode, String errorDetail)
    : result = null,
      errorCode = errorCode,
      errorDetail = errorDetail {
  _validateErrorCode(errorCode);
  // TODO: When NNBD is complete, delete the following line.
  checkNotNullable(errorDetail, "errorDetail");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/ServiceExtensionResponse/ServiceExtensionResponse.error.html>
:::
