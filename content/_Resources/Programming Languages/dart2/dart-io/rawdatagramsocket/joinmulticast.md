[dart:io](../../dart-io/dart-io-library){._links-link}

joinMulticast method
====================

::: {.section .multi-line-signature}
void joinMulticast(

1.  [InternetAddress](../internetaddress-class) group,
2.  \[[NetworkInterface](../networkinterface-class)? interface\]

)
:::

Joins a multicast group.

If an error occur when trying to join the multicast group, an exception
is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void joinMulticast(InternetAddress group, [NetworkInterface? interface]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket/joinMulticast.html>
:::
