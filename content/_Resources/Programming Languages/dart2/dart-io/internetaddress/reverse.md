[dart:io](../../dart-io/dart-io-library){._links-link}

reverse method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[InternetAddress](../internetaddress-class)\>
reverse()
:::

Performs a reverse DNS lookup on this [address](address)

Returns a new `InternetAddress` with the same address, but where the
[host](host) field set to the result of the lookup.

If this address is Unix domain addresses, no lookup is performed and
this address is returned directly.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<InternetAddress> reverse();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddress/reverse.html>
:::
