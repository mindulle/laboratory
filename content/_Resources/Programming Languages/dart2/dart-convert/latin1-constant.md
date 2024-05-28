[dart:convert](../dart-convert/dart-convert-library){._links-link}

latin1 top-level constant
=========================

::: {.section .multi-line-signature}
[Latin1Codec](latin1codec-class) const latin1
:::

An instance of the default implementation of the
[Latin1Codec](latin1codec-class).

This instance provides a convenient access to the most common ISO Latin
1 use cases.

Examples:

``` {.language-dart data-language="dart"}
var encoded = latin1.encode("blåbærgrød");
var decoded = latin1.decode([0x62, 0x6c, 0xe5, 0x62, 0xe6,
                             0x72, 0x67, 0x72, 0xf8, 0x64]);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Latin1Codec latin1 = Latin1Codec();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/latin1-constant.html>
:::
