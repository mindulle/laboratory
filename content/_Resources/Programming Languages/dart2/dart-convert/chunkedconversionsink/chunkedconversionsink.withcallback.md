[dart:convert](../../dart-convert/dart-convert-library){._links-link}

ChunkedConversionSink\<T\>.withCallback constructor
===================================================

::: {.section .multi-line-signature}
ChunkedConversionSink\<T\>.withCallback(

1.  void callback(
    1.  [List](../../dart-core/list-class)\<T\> accumulated

    )

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ChunkedConversionSink.withCallback(
    void callback(List<T> accumulated)) = _SimpleCallbackSink<T>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/ChunkedConversionSink/ChunkedConversionSink.withCallback.html>
:::
