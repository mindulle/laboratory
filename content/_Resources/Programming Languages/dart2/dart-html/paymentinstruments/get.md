[dart:html](../../dart-html/dart-html-library){._links-link}

get method
==========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
dynamic\>?\> get(

1.  [String](../../dart-core/string-class) instrumentKey

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Map<String, dynamic>?> get(String instrumentKey) =>
    promiseToFutureAsMap(JS("", "#.get(#)", this, instrumentKey));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PaymentInstruments/get.html>
:::
