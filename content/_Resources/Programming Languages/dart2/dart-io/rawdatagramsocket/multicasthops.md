[dart:io](../../dart-io/dart-io-library){._links-link}

multicastHops property
======================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) multicastHops

::: {.features}
read / write
:::
:::

The maximum network hops for multicast packages originating from this
socket.

For IPv4 this is referred to as TTL (time to live).

By default this value is 1 causing multicast traffic to stay on the
local network.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
abstract int multicastHops;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket/multicastHops.html>
:::
