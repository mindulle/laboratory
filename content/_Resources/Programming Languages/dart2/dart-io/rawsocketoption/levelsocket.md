[dart:io](../../dart-io/dart-io-library){._links-link}

levelSocket property
====================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) levelSocket
:::

Socket level option for `SOL_SOCKET`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int get levelSocket =>
    _getOptionValue(_RawSocketOptions.SOL_SOCKET.index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/levelSocket.html>
:::
