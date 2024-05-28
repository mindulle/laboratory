[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

handler property
================

::: {#setter .section .multi-line-signature}
void handler=([Function](../../dart-core/function-class)? newHandler)
:::

Sets the handler that is invoked for every incoming message.

The handler is invoked in the
[Zone.root](../../dart-async/zone/root-constant) zone. If the handler
should be invoked in the current zone, do:

``` {.language-dart data-language="dart"}
rawPort.handler = Zone.current.bindCallback(actualHandler);
```

The handler must be a function which can accept one argument of the type
of the messages sent to this port. This means that if it is known that
messages will all be [String](../../dart-core/string-class)s, a handler
of type `void Function(String)` can be used. The function is invoked
dynamically with the actual messages, and if this invocation fails, the
error becomes a top-level uncaught error in the
[Zone.root](../../dart-async/zone/root-constant) zone.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// TODO(44659): Change parameter type to `void Function(Never)` to only
// accept functions which can be called with one argument.
void set handler(Function? newHandler);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/RawReceivePort/handler.html>
:::
