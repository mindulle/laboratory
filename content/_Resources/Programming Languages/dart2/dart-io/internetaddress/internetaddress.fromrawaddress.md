[dart:io](../../dart-io/dart-io-library){._links-link}

InternetAddress.fromRawAddress constructor
==========================================

::: {.section .multi-line-signature}
InternetAddress.fromRawAddress(

1.  [Uint8List](../../dart-typed_data/uint8list-class) rawAddress,
2.  {\@Since(\"2.8\")
    [InternetAddressType](../internetaddresstype-class)? type}

)
:::

Creates a new [InternetAddress](../internetaddress-class) from the
provided raw address bytes.

If the `type` is
[InternetAddressType.IPv4](../internetaddresstype/ipv4-constant), the
`rawAddress` must have length 4. If the `type` is
[InternetAddressType.IPv6](../internetaddresstype/ipv6-constant), the
`rawAddress` must have length 16. If the `type` is
[InternetAddressType.unix](../internetaddresstype/unix-constant), the
`rawAddress` must be a valid UTF-8 encoded file path.

If `type` is omitted, the `rawAddress` must have a length of either 4 or
16, in which case the type defaults to
[InternetAddressType.IPv4](../internetaddresstype/ipv4-constant) or
[InternetAddressType.IPv6](../internetaddresstype/ipv6-constant)
respectively.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory InternetAddress.fromRawAddress(Uint8List rawAddress,
    {@Since("2.8") InternetAddressType? type});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddress/InternetAddress.fromRawAddress.html>
:::
