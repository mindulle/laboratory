[dart:developer](../dart-developer/dart-developer-library){._links-link}

extensionStreamHasListener top-level property
=============================================

::: {#getter .section .multi-line-signature}
[bool](../dart-core/bool-class) extensionStreamHasListener
:::

Whether the \"Extension\" stream currently has at least one listener.

A client of the VM service can register as a listener on the extension
stream using `listenStream` method. The extension stream has a listener
while at least one such client has registered as a listener, and has not
yet disconnected again.

Calling [postEvent](postevent) while the stream has listeners will
attempt to deliver that event to all current listeners, although a
listener can disconnect before the event is delivered. Calling
[postEvent](postevent) when the stream has no listener means that no-one
will receive the event, and the call is effectively a no-op.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:recognized", "other")
@pragma("vm:prefer-inline")
external bool get extensionStreamHasListener;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/extensionStreamHasListener.html>
:::
