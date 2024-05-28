[dart:convert](../../dart-convert/dart-convert-library){._links-link}

StringConversionSink.fromStringSink constructor
===============================================

::: {.section .multi-line-signature}
StringConversionSink.fromStringSink(

1.  [StringSink](../../dart-core/stringsink-class) sink

)
:::

Creates a new instance wrapping the given `sink`.

Every string that is added to the returned instance is forwarded to the
`sink`. The instance is allowed to buffer and is not required to forward
immediately.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StringConversionSink.fromStringSink(StringSink sink) =
    _StringSinkConversionSink<StringSink>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/StringConversionSink/StringConversionSink.fromStringSink.html>
:::
