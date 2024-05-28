[dart:io](../../dart-io/dart-io-library){._links-link}

broadcastEnabled property
=========================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) broadcastEnabled

::: {.features}
read / write
:::
:::

Whether IPv4 broadcast is enabled.

IPv4 broadcast needs to be enabled by the sender for sending IPv4
broadcast packages. By default IPv4 broadcast is disabled.

For IPv6 there is no general broadcast mechanism. Use multicast instead.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
abstract bool broadcastEnabled;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket/broadcastEnabled.html>
:::
