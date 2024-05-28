[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

removeErrorListener method
==========================

::: {.section .multi-line-signature}
void removeErrorListener(

1.  [SendPort](../sendport-class) port

)
:::

Stops listening for uncaught errors from the isolate.

Requests for the isolate to not send uncaught errors on `port`. If the
isolate isn\'t expecting to send uncaught errors on `port`, because the
port hasn\'t been added using [addErrorListener](adderrorlistener), or
because it has already been removed, the request is ignored.

If the same port has been passed via
[addErrorListener](adderrorlistener) more than once, only one call to
`removeErrorListener` is needed to stop it from receiving uncaught
errors.

Uncaught errors message may still be sent by the isolate until this
request is received and processed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void removeErrorListener(SendPort port);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/removeErrorListener.html>
:::
