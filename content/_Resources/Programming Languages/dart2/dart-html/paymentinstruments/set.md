[dart:html](../../dart-html/dart-html-library){._links-link}

set method
==========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) set(

1.  [String](../../dart-core/string-class) instrumentKey,
2.  [Map](../../dart-core/map-class) details

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future set(String instrumentKey, Map details) {
  var details_dict = convertDartToNative_Dictionary(details);
  return promiseToFuture(
      JS("", "#.set(#, #)", this, instrumentKey, details_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PaymentInstruments/set.html>
:::
