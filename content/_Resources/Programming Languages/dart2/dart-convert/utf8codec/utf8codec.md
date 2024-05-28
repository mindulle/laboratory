[dart:convert](../../dart-convert/dart-convert-library){._links-link}

Utf8Codec constructor
=====================

::: {.section .multi-line-signature}
const Utf8Codec(

1.  {[bool](../../dart-core/bool-class) allowMalformed = false}

)
:::

Instantiates a new [Utf8Codec](../utf8codec-class).

The optional `allowMalformed` argument defines how [decoder](decoder)
(and [decode](decode)) deal with invalid or unterminated character
sequences.

If it is `true` (and not overridden at the method invocation)
[decode](decode) and the [decoder](decoder) replace invalid (or
unterminated) octet sequences with the Unicode Replacement character
`U+FFFD` (�). Otherwise they throw a
[FormatException](../../dart-core/formatexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Utf8Codec({bool allowMalformed = false})
    : _allowMalformed = allowMalformed;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Codec/Utf8Codec.html>
:::
