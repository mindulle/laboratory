[dart:convert](../../dart-convert/dart-convert-library){._links-link}

Latin1Codec constructor
=======================

::: {.section .multi-line-signature}
const Latin1Codec(

1.  {[bool](../../dart-core/bool-class) allowInvalid = false}

)
:::

Instantiates a new [Latin1Codec](../latin1codec-class).

If `allowInvalid` is true, the [decode](decode) method and the converter
returned by [decoder](decoder) will default to allowing invalid values.
Invalid values are decoded into the Unicode Replacement character
(U+FFFD). Calls to the [decode](decode) method can override this
default.

Encoders will not accept invalid (non Latin-1) characters.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Latin1Codec({bool allowInvalid = false}) : _allowInvalid = allowInvalid;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Codec/Latin1Codec.html>
:::
