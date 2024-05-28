[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

addErrorListener method
=======================

::: {.section .multi-line-signature}
void addErrorListener(

1.  [SendPort](../sendport-class) port

)
:::

Requests that uncaught errors of the isolate are sent back to `port`.

The errors are sent back as two-element lists. The first element is a
`String` representation of the error, usually created by calling
`toString` on the error. The second element is a `String` representation
of an accompanying stack trace, or `null` if no stack trace was
provided. To convert this back to a
[StackTrace](../../dart-core/stacktrace-class) object, use
[StackTrace.fromString](../../dart-core/stacktrace/stacktrace.fromstring).

Listening using the same port more than once does nothing. A port will
only receive each error once, and will only need to be removed once
using [removeErrorListener](removeerrorlistener).

Closing the receive port that is associated with the port does not stop
the isolate from sending uncaught errors, they are just going to be
lost. Instead use [removeErrorListener](removeerrorlistener) to stop
receiving errors on `port`.

Since isolates run concurrently, it\'s possible for it to exit before
the error listener is established. To avoid this, start the isolate
paused, add the listener and then resume the isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void addErrorListener(SendPort port);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/addErrorListener.html>
:::
