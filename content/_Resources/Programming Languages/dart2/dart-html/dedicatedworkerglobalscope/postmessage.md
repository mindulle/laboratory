[dart:html](../../dart-html/dart-html-library){._links-link}

postMessage method
==================

::: {.section .multi-line-signature}
void postMessage(

1.  dynamic message,
2.  \[[List](../../dart-core/list-class)\<[Object](../../dart-core/object-class)\>?
    transfer\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void postMessage(/*any*/ message, [List<Object>? transfer]) {
  if (transfer != null) {
    var message_1 = convertDartToNative_SerializedScriptValue(message);
    _postMessage_1(message_1, transfer);
    return;
  }
  var message_1 = convertDartToNative_SerializedScriptValue(message);
  _postMessage_2(message_1);
  return;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DedicatedWorkerGlobalScope/postMessage.html>
:::
