[dart:developer](../../dart-developer/dart-developer-library){._links-link}

getIsolateID method
===================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class)? getIsolateID(

1.  [Isolate](../../dart-isolate/isolate-class) isolate

)
:::

Returns a [String](../../dart-core/string-class) token representing the
ID of `isolate`.

Returns null if the running Dart environment does not support the
service protocol.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String? getIsolateID(Isolate isolate) {
  // TODO: When NNBD is complete, delete the following line.
  ArgumentError.checkNotNull(isolate, 'isolate');
  return _getIsolateIDFromSendPort(isolate.controlPort);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Service/getIsolateID.html>
:::
