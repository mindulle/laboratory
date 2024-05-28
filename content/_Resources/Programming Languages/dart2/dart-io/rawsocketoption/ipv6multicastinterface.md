[dart:io](../../dart-io/dart-io-library){._links-link}

IPv6MulticastInterface property
===============================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) IPv6MulticastInterface
:::

Socket option for `IPV6_MULTICAST_IF`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int get IPv6MulticastInterface =>
    _getOptionValue(_RawSocketOptions.IPV6_MULTICAST_IF.index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/IPv6MulticastInterface.html>
:::
