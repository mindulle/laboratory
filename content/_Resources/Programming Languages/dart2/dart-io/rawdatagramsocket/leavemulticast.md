[dart:io](../../dart-io/dart-io-library){._links-link}

leaveMulticast method
=====================

::: {.section .multi-line-signature}
void leaveMulticast(

1.  [InternetAddress](../internetaddress-class) group,
2.  \[[NetworkInterface](../networkinterface-class)? interface\]

)
:::

Leaves a multicast group.

If an error occur when trying to join the multicast group, an exception
is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void leaveMulticast(InternetAddress group, [NetworkInterface? interface]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket/leaveMulticast.html>
:::
