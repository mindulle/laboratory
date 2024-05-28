[dart:convert](../dart-convert/dart-convert-library){._links-link}

base64Decode function
=====================

::: {.section .multi-line-signature}
[Uint8List](../dart-typed_data/uint8list-class) base64Decode(

1.  [String](../dart-core/string-class) source

)
:::

Decodes [base64](https://tools.ietf.org/html/rfc4648) or
[base64url](https://tools.ietf.org/html/rfc4648) encoded bytes.

Shorthand for `base64.decode(bytes)`. Useful if a local variable shadows
the global [base64](base64-constant) constant.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List base64Decode(String source) => base64.decode(source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/base64Decode.html>
:::
