[dart:convert](../../dart-convert/dart-convert-library){._links-link}

startChunkedConversion method
=============================

::: {.section .multi-line-signature}
[StringConversionSink](../stringconversionsink-class)
startChunkedConversion(

1.  [Sink](../../dart-core/sink-class)\<[String](../../dart-core/string-class)\>
    sink

)

::: {.features}
override
:::
:::

Starts a chunked conversion.

The returned sink serves as input for the long-running conversion. The
given `sink` serves as output.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
StringConversionSink startChunkedConversion(Sink<String> sink) {
  return _HtmlEscapeSink(this,
      sink is StringConversionSink ? sink : StringConversionSink.from(sink));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscape/startChunkedConversion.html>
:::
