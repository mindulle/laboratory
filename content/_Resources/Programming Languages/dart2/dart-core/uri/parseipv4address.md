[dart:core](../../dart-core/dart-core-library){._links-link}

parseIPv4Address method
=======================

::: {.section .multi-line-signature}
[List](../list-class)\<[int](../int-class)\> parseIPv4Address(

1.  [String](../string-class) host

)
:::

Parses the `host` as an IP version 4 (IPv4) address, returning the
address as a list of 4 bytes in network byte order (big endian).

Throws a [FormatException](../formatexception-class) if `host` is not a
valid IPv4 address representation.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static List<int> parseIPv4Address(String host) =>
    _parseIPv4Address(host, 0, host.length);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/parseIPv4Address.html>
:::
