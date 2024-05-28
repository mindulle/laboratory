[dart:convert](../../dart-convert/dart-convert-library){._links-link}

asUtf8Sink method
=================

::: {.section .multi-line-signature}
[ByteConversionSink](../byteconversionsink-class) asUtf8Sink(

1.  [bool](../../dart-core/bool-class) allowMalformed

)
:::

Returns `this` as a sink that accepts UTF-8 input.

If used, this method must be the first and only call to `this`. It
invalidates `this`. All further operations must be performed on the
result.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ByteConversionSink asUtf8Sink(bool allowMalformed);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/StringConversionSink/asUtf8Sink.html>
:::
