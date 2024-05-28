[dart:io](../../dart-io/dart-io-library){._links-link}

list method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[List](../../dart-core/list-class)\<[NetworkInterface](../networkinterface-class)\>\>
list(

1.  {[bool](../../dart-core/bool-class) includeLoopback = false,
2.  [bool](../../dart-core/bool-class) includeLinkLocal = false,
3.  [InternetAddressType](../internetaddresstype-class) type =
    InternetAddressType.any}

)
:::

Query the system for [NetworkInterface](../networkinterface-class)s.

If `includeLoopback` is `true`, the returned list will include the
loopback device. Default is `false`.

If `includeLinkLocal` is `true`, the list of addresses of the returned
[NetworkInterface](../networkinterface-class)s, may include link local
addresses. Default is `false`.

If `type` is either
[InternetAddressType.IPv4](../internetaddresstype/ipv4-constant) or
[InternetAddressType.IPv6](../internetaddresstype/ipv6-constant) it will
only lookup addresses of the specified type. Default is
[InternetAddressType.any](../internetaddresstype/any-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Future<List<NetworkInterface>> list(
    {bool includeLoopback = false,
    bool includeLinkLocal = false,
    InternetAddressType type = InternetAddressType.any});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/NetworkInterface/list.html>
:::
