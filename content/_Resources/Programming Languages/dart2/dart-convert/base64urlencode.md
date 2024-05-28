[dart:convert](../dart-convert/dart-convert-library){._links-link}

base64UrlEncode function
========================

::: {.section .multi-line-signature}
[String](../dart-core/string-class) base64UrlEncode(

1.  [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
    bytes

)
:::

Encodes `bytes` using [base64url](https://tools.ietf.org/html/rfc4648)
encoding.

Shorthand for `base64url.encode(bytes)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String base64UrlEncode(List<int> bytes) => base64Url.encode(bytes);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/base64UrlEncode.html>
:::
