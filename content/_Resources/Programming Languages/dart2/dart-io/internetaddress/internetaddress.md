[dart:io](../../dart-io/dart-io-library){._links-link}

InternetAddress constructor
===========================

::: {.section .multi-line-signature}
InternetAddress(

1.  [String](../../dart-core/string-class) address,
2.  {\@Since(\"2.8\")
    [InternetAddressType](../internetaddresstype-class)? type}

)
:::

Creates a new [InternetAddress](../internetaddress-class) from a numeric
address or a file path.

If `type` is
[InternetAddressType.IPv4](../internetaddresstype/ipv4-constant),
`address` must be a numeric IPv4 address (dotted-decimal notation). If
`type` is
[InternetAddressType.IPv6](../internetaddresstype/ipv6-constant),
`address` must be a numeric IPv6 address (hexadecimal notation). If
`type` is
[InternetAddressType.unix](../internetaddresstype/unix-constant),
`address` must be a a valid file path. If `type` is omitted, `address`
must be either a numeric IPv4 or IPv6 address and the type is inferred
from the format.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory InternetAddress(String address,
    {@Since("2.8") InternetAddressType? type});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddress/InternetAddress.html>
:::
