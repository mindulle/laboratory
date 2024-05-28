[dart:io](../../dart-io/dart-io-library){._links-link}

level property
==============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) level
:::

A platform specific value used to determine the kind of control message.

Together with [type](type), these two integers identify the kind of
control message in a platform specific way. For example, on Linux
certain combinations of these values indicate that this is a control
message that carries [ResourceHandle](../resourcehandle-class)s.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get level;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketControlMessage/level.html>
:::
