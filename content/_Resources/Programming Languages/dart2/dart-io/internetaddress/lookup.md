[dart:io](../../dart-io/dart-io-library){._links-link}

lookup method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[List](../../dart-core/list-class)\<[InternetAddress](../internetaddress-class)\>\>
lookup(

1.  [String](../../dart-core/string-class) host,
2.  {[InternetAddressType](../internetaddresstype-class) type =
    InternetAddressType.any}

)
:::

Looks up the addresses of a host.

If `type` is
[InternetAddressType.any](../internetaddresstype/any-constant), it will
lookup both IP version 4 (IPv4) and IP version 6 (IPv6) addresses. If
`type` is either
[InternetAddressType.IPv4](../internetaddresstype/ipv4-constant) or
[InternetAddressType.IPv6](../internetaddresstype/ipv6-constant) it will
only lookup addresses of the specified type. The order of the list can,
and most likely will, change over time.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Future<List<InternetAddress>> lookup(String host,
    {InternetAddressType type = InternetAddressType.any});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddress/lookup.html>
:::
