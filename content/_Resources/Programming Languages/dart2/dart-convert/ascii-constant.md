[dart:convert](../dart-convert/dart-convert-library){._links-link}

ascii top-level constant
========================

::: {.section .multi-line-signature}
[AsciiCodec](asciicodec-class) const ascii
:::

An instance of the default implementation of the
[AsciiCodec](asciicodec-class).

This instance provides a convenient access to the most common ASCII use
cases.

Examples:

``` {.language-dart data-language="dart"}
var encoded = ascii.encode("This is ASCII!");
var decoded = ascii.decode([0x54, 0x68, 0x69, 0x73, 0x20, 0x69, 0x73,
                            0x20, 0x41, 0x53, 0x43, 0x49, 0x49, 0x21]);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const AsciiCodec ascii = AsciiCodec();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/ascii-constant.html>
:::
