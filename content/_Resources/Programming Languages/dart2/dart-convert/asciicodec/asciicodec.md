[dart:convert](../../dart-convert/dart-convert-library){._links-link}

AsciiCodec constructor
======================

::: {.section .multi-line-signature}
const AsciiCodec(

1.  {[bool](../../dart-core/bool-class) allowInvalid = false}

)
:::

Instantiates a new [AsciiCodec](../asciicodec-class).

If `allowInvalid` is true, the [decode](decode) method and the converter
returned by [decoder](decoder) will default to allowing invalid values.
If allowing invalid values, the values will be decoded into the Unicode
Replacement character (U+FFFD). If not, an exception will be thrown.
Calls to the [decode](decode) method can choose to override this
default.

Encoders will not accept invalid (non ASCII) characters.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const AsciiCodec({bool allowInvalid = false}) : _allowInvalid = allowInvalid;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/AsciiCodec/AsciiCodec.html>
:::
