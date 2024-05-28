[dart:io](../../dart-io/dart-io-library){._links-link}

multicastInterface property
===========================

::: {.section .multi-line-signature}
[NetworkInterface](../networkinterface-class)? multicastInterface

::: {.features}
@[Deprecated](../../dart-core/deprecated-class)(\"This property is not
implemented. Use getRawOption and \" \"setRawOption instead.\"), read /
write
:::
:::

The network interface used for outgoing multicast packages.

A value of `null` indicate that the system chooses the network interface
to use.

By default this value is `null`

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("This property is not implemented. Use getRawOption and "
    "setRawOption instead.")
NetworkInterface? multicastInterface;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket/multicastInterface.html>
:::
