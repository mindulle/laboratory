[dart:io](../../dart-io/dart-io-library){._links-link}

extractHandles method
=====================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[ResourceHandle](../resourcehandle-class)\>
extractHandles()
:::

Extracts the list of handles embedded in this message.

This method must only be used to extract handles from messages received
on a socket. It must not be used on a socket control message that is
created locally, and has not been sent using
[RawSocket.sendMessage](../rawsocket/sendmessage).

This method must only be called once. Calling it multiple times may
cause duplicated handles with unspecified behavior.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<ResourceHandle> extractHandles();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketControlMessage/extractHandles.html>
:::
