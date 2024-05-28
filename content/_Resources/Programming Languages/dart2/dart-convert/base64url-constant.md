[dart:convert](../dart-convert/dart-convert-library){._links-link}

base64Url top-level constant
============================

::: {.section .multi-line-signature}
[Base64Codec](base64codec-class) const base64Url
:::

A [base64url](https://tools.ietf.org/html/rfc4648) encoder and decoder.

It encodes and decodes using the base64url alphabet, decodes using both
the base64 and base64url alphabets, does not allow invalid characters
and requires padding.

Examples:

``` {.language-dart data-language="dart"}
var encoded = base64Url.encode([0x62, 0x6c, 0xc3, 0xa5, 0x62, 0xc3, 0xa6,
                                0x72, 0x67, 0x72, 0xc3, 0xb8, 0x64]);
var decoded = base64Url.decode("YmzDpWLDpnJncsO4ZAo=");
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Base64Codec base64Url = Base64Codec.urlSafe();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/base64Url-constant.html>
:::
