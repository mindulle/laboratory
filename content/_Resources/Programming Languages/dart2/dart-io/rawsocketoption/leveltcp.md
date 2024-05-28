[dart:io](../../dart-io/dart-io-library){._links-link}

levelTcp property
=================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) levelTcp
:::

Socket level option for `IPPROTO_TCP`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int get levelTcp =>
    _getOptionValue(_RawSocketOptions.IPPROTO_TCP.index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/levelTcp.html>
:::
