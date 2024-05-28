[dart:io](../../dart-io/dart-io-library){._links-link}

rawAddress property
===================

::: {#getter .section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) rawAddress
:::

The raw address of this [InternetAddress](../internetaddress-class).

For an IP address, the result is either a 4 or 16 byte long list. For a
Unix domain address, UTF-8 encoded byte sequences that represents
[address](address) is returned.

The returned list is a fresh copy, making it possible to change the list
without modifying the [InternetAddress](../internetaddress-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List get rawAddress;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddress/rawAddress.html>
:::
