[dart:convert](../../dart-convert/dart-convert-library){._links-link}

Latin1Decoder constructor
=========================

::: {.section .multi-line-signature}
const Latin1Decoder(

1.  {[bool](../../dart-core/bool-class) allowInvalid = false}

)
:::

Instantiates a new [Latin1Decoder](../latin1decoder-class).

The optional `allowInvalid` argument defines how [convert](convert)
deals with invalid bytes.

If it is `true`, [convert](convert) replaces invalid bytes with the
Unicode Replacement character `U+FFFD` (�). Otherwise it throws a
[FormatException](../../dart-core/formatexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Latin1Decoder({bool allowInvalid = false})
    : super(allowInvalid, _latin1Mask);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Decoder/Latin1Decoder.html>
:::
