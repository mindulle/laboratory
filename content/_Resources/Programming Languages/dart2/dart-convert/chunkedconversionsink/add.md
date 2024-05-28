[dart:convert](../../dart-convert/dart-convert-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  T chunk

)

::: {.features}
override
:::
:::

Adds chunked data to this sink.

This method is also used when converters are used as
[StreamTransformer](../../dart-async/streamtransformer-class)s.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(T chunk);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/ChunkedConversionSink/add.html>
:::
