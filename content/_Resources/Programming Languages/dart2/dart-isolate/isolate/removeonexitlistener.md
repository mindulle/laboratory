[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

removeOnExitListener method
===========================

::: {.section .multi-line-signature}
void removeOnExitListener(

1.  [SendPort](../sendport-class) responsePort

)
:::

Stops listening for exit messages from the isolate.

Requests for the isolate to not send exit messages on `responsePort`. If
the isolate isn\'t expecting to send exit messages on `responsePort`,
because the port hasn\'t been added using
[addOnExitListener](addonexitlistener), or because it has already been
removed, the request is ignored.

If the same port has been passed via
[addOnExitListener](addonexitlistener) more than once, only one call to
`removeOnExitListener` is needed to stop it from receiving exit
messages.

Closing the receive port that is associated with the `responsePort` does
not stop the isolate from sending uncaught errors, they are just going
to be lost.

An exit message may still be sent if the isolate terminates before this
request is received and processed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void removeOnExitListener(SendPort responsePort);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/removeOnExitListener.html>
:::
