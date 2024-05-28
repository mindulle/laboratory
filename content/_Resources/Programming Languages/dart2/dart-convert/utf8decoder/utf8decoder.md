[dart:convert](../../dart-convert/dart-convert-library){._links-link}

Utf8Decoder constructor
=======================

::: {.section .multi-line-signature}
const Utf8Decoder(

1.  {[bool](../../dart-core/bool-class) allowMalformed = false}

)
:::

Instantiates a new [Utf8Decoder](../utf8decoder-class).

The optional `allowMalformed` argument defines how [convert](convert)
deals with invalid or unterminated character sequences.

If it is `true`, [convert](convert) replaces invalid (or unterminated)
character sequences with the Unicode Replacement character `U+FFFD` (�).
Otherwise it throws a
[FormatException](../../dart-core/formatexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Utf8Decoder({bool allowMalformed = false})
    : _allowMalformed = allowMalformed;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Decoder/Utf8Decoder.html>
:::
