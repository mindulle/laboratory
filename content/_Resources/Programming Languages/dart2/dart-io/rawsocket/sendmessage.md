[dart:io](../../dart-io/dart-io-library){._links-link}

sendMessage method
==================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.15\")

</div>

[int](../../dart-core/int-class) sendMessage(

1.  [List](../../dart-core/list-class)\<[SocketControlMessage](../socketcontrolmessage-class)\>
    controlMessages,
2.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    data,
3.  \[[int](../../dart-core/int-class) offset = 0,
4.  [int](../../dart-core/int-class)? count\]

)

::: {.features}
\@Since(\"2.15\")
:::
:::

Writes socket control messages and data bytes to the socket.

Writes `controlMessages` and up to `count` bytes of `data`, starting at
`offset`, to the socket. If `count` is not provided, as many bytes as
possible are written. Use [write](write) instead if no control messages
are required to be sent.

When sent control messages are received, they are retained until the
next call to [readMessage](readmessage), where all currently available
control messages are provided as part of the returned
[SocketMessage](../socketmessage-class). Calling [read](read) will read
only data bytes, and will not affect control messages.

The `count` must be positive (greater than zero).

Returns the number of bytes written, which cannot be greater than
`count`, nor greater than `data.length - offset`. Return value of zero
indicates that control messages were not sent.

This function is non-blocking and will only write data if buffer space
is available in the socket.

Throws an [OSError](../oserror-class) if message could not be sent out.

Unsupported by [RawSecureSocket](../rawsecuresocket-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.15")
int sendMessage(List<SocketControlMessage> controlMessages, List<int> data,
    [int offset = 0, int? count]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocket/sendMessage.html>
:::
