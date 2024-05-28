[dart:io](../../dart-io/dart-io-library){._links-link}

setOption method
================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) setOption(

1.  [SocketOption](../socketoption-class) option,
2.  [bool](../../dart-core/bool-class) enabled

)
:::

Customizes the [RawSocket](../rawsocket-class).

See [SocketOption](../socketoption-class) for available options.

Returns `true` if the option was set successfully, false otherwise.

Throws a [SocketException](../socketexception-class) if the socket has
been destroyed or upgraded to a secure socket.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool setOption(SocketOption option, bool enabled);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Socket/setOption.html>
:::
