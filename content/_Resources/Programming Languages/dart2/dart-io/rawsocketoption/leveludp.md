[dart:io](../../dart-io/dart-io-library){._links-link}

levelUdp property
=================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) levelUdp
:::

Socket level option for `IPPROTO_UDP`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int get levelUdp =>
    _getOptionValue(_RawSocketOptions.IPPROTO_UDP.index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/levelUdp.html>
:::
