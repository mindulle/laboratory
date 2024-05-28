[dart:io](../../dart-io/dart-io-library){._links-link}

serverSocketBind method
=======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[ServerSocket](../serversocket-class)\>
serverSocketBind(

1.  dynamic address,
2.  [int](../../dart-core/int-class) port,
3.  {[int](../../dart-core/int-class) backlog = 0,
4.  [bool](../../dart-core/bool-class) v6Only = false,
5.  [bool](../../dart-core/bool-class) shared = false}

)
:::

Asynchronously returns a `ServerSocket` that connects to the given
address and port when successful.

When this override is installed, this functions overrides the behavior
of `ServerSocket.bind(...)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<ServerSocket> serverSocketBind(address, int port,
    {int backlog = 0, bool v6Only = false, bool shared = false}) {
  return ServerSocket._bind(address, port,
      backlog: backlog, v6Only: v6Only, shared: shared);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/serverSocketBind.html>
:::
