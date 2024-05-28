[dart:convert](../dart-convert/dart-convert-library){._links-link}

base64Encode function
=====================

::: {.section .multi-line-signature}
[String](../dart-core/string-class) base64Encode(

1.  [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
    bytes

)
:::

Encodes `bytes` using [base64](https://tools.ietf.org/html/rfc4648)
encoding.

Shorthand for `base64.encode(bytes)`. Useful if a local variable shadows
the global [base64](base64-constant) constant.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String base64Encode(List<int> bytes) => base64.encode(bytes);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/base64Encode.html>
:::
