[dart:convert](../../dart-convert/dart-convert-library){._links-link}

startChunkedConversion method
=============================

::: {.section .multi-line-signature}
[StringConversionSink](../stringconversionsink-class)
startChunkedConversion(

1.  [Sink](../../dart-core/sink-class)\<[Object](../../dart-core/object-class)?\>
    sink

)

::: {.features}
override
:::
:::

Starts a conversion from a chunked JSON string to its corresponding
object.

The output `sink` receives exactly one decoded element through `add`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external StringConversionSink startChunkedConversion(Sink<Object?> sink);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonDecoder/startChunkedConversion.html>
:::
