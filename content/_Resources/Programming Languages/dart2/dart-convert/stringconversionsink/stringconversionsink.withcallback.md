[dart:convert](../../dart-convert/dart-convert-library){._links-link}

StringConversionSink.withCallback constructor
=============================================

::: {.section .multi-line-signature}
StringConversionSink.withCallback(

1.  void callback(
    1.  [String](../../dart-core/string-class) accumulated

    )

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StringConversionSink.withCallback(void callback(String accumulated)) =
    _StringCallbackSink;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/StringConversionSink/StringConversionSink.withCallback.html>
:::
