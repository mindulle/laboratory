[dart:io](../../dart-io/dart-io-library){._links-link}

readMessage method
==================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.15\")

</div>

[SocketMessage](../socketmessage-class)? readMessage(

1.  \[[int](../../dart-core/int-class)? count\]

)

::: {.features}
\@Since(\"2.15\")
:::
:::

Reads a message containing up to `count` bytes from the socket.

This function differs from [read](read) in that it will also return any
[SocketControlMessage](../socketcontrolmessage-class) that have been
sent.

This function is non-blocking and will only return data if data is
available. The number of bytes read can be less then `count` if fewer
bytes are available for immediate reading. Length of data buffer in
[SocketMessage](../socketmessage-class) indicates number of bytes read.

Returns `null` if no data is available.

Unsupported by [RawSecureSocket](../rawsecuresocket-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.15")
SocketMessage? readMessage([int? count]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocket/readMessage.html>
:::
