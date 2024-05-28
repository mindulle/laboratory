[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

addOnExitListener method
========================

::: {.section .multi-line-signature}
void addOnExitListener(

1.  [SendPort](../sendport-class) responsePort,
2.  {[Object](../../dart-core/object-class)? response}

)
:::

Requests an exit message on `responsePort` when the isolate terminates.

The isolate will send `response` as a message on `responsePort` as the
last thing before it terminates. It will run no further code after the
message has been sent.

Adding the same port more than once will only cause it to receive one
exit message, using the last response value that was added, and it only
needs to be removed once using
[removeOnExitListener](removeonexitlistener).

If the isolate has terminated before it can receive this request, no
exit message will be sent.

The `response` object must follow the same restrictions as enforced by
[SendPort.send](../sendport/send). It is recommended to only use simple
values that can be sent to all isolates, like `null`, booleans, numbers
or strings.

Since isolates run concurrently, it\'s possible for it to exit before
the exit listener is established, and in that case no response will be
sent on `responsePort`. To avoid this, either use the corresponding
parameter to the spawn function, or start the isolate paused, add the
listener and then resume the isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
/* TODO(lrn): Can we do better? Can the system recognize this message and
 * send a reply if the receiving isolate is dead?
 */
external void addOnExitListener(SendPort responsePort, {Object? response});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/addOnExitListener.html>
:::
