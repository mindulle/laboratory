[dart:io](../../dart-io/dart-io-library){._links-link}

tryParse method
===============

::: {.section .multi-line-signature}
[InternetAddress](../internetaddress-class)? tryParse(

1.  [String](../../dart-core/string-class) address

)
:::

Attempts to parse `address` as a numeric address.

Returns `null` If `address` is not a numeric IPv4 (dotted-decimal
notation) or IPv6 (hexadecimal representation) address.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static InternetAddress? tryParse(String address);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddress/tryParse.html>
:::
