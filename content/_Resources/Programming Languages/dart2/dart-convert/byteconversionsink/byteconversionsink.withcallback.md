[dart:convert](../../dart-convert/dart-convert-library){._links-link}

ByteConversionSink.withCallback constructor
===========================================

::: {.section .multi-line-signature}
ByteConversionSink.withCallback(

1.  void callback(
    1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
        accumulated

    )

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ByteConversionSink.withCallback(
    void callback(List<int> accumulated)) = _ByteCallbackSink;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/ByteConversionSink/ByteConversionSink.withCallback.html>
:::
