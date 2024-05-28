[dart:io](../../dart-io/dart-io-library){._links-link}

SocketControlMessage.fromHandles constructor
============================================

::: {.section .multi-line-signature}
SocketControlMessage.fromHandles(

1.  [List](../../dart-core/list-class)\<[ResourceHandle](../resourcehandle-class)\>
    handles

)
:::

Creates a control message containing the provided `handles`.

This is used by the sender when it sends handles across the socket.
Receiver can extract the handles from the message using
[extractHandles](extracthandles).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory SocketControlMessage.fromHandles(
    List<ResourceHandle> handles);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketControlMessage/SocketControlMessage.fromHandles.html>
:::
