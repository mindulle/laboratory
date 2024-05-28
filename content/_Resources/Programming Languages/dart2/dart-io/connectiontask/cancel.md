[dart:io](../../dart-io/dart-io-library){._links-link}

cancel method
=============

::: {.section .multi-line-signature}
void cancel()
:::

Cancels the connection attempt.

This also causes the [socket](socket) `Future` to complete with a
[SocketException](../socketexception-class) error.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void cancel() {
  _onCancel();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ConnectionTask/cancel.html>
:::
