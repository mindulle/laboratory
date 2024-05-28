[dart:convert](../dart-convert/dart-convert-library){._links-link}

utf8 top-level constant
=======================

::: {.section .multi-line-signature}
[Utf8Codec](utf8codec-class) const utf8
:::

An instance of the default implementation of the
[Utf8Codec](utf8codec-class).

This instance provides a convenient access to the most common UTF-8 use
cases.

Examples:

``` {.language-dart data-language="dart"}
var encoded = utf8.encode("Îñţérñåţîöñåļîžåţîờñ");
var decoded = utf8.decode([0x62, 0x6c, 0xc3, 0xa5, 0x62, 0xc3, 0xa6,
                           0x72, 0x67, 0x72, 0xc3, 0xb8, 0x64]);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Utf8Codec utf8 = Utf8Codec();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/utf8-constant.html>
:::
