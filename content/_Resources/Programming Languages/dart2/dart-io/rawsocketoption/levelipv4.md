[dart:io](../../dart-io/dart-io-library){._links-link}

levelIPv4 property
==================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) levelIPv4
:::

Socket level option for `IPPROTO_IP`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int get levelIPv4 =>
    _getOptionValue(_RawSocketOptions.IPPROTO_IP.index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/levelIPv4.html>
:::
