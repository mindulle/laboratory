[dart:io](../../dart-io/dart-io-library){._links-link}

data property
=============

::: {#getter .section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) data
:::

Actual bytes that were passed as part of the control message by the
underlying platform.

The bytes are interpreted differently depending on the [level](level)
and [type](type). These actual bytes can be used to inspect and
interpret non-handle-carrying messages.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List get data;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketControlMessage/data.html>
:::
