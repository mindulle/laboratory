[dart:html](../../dart-html/dart-html-library){._links-link}

PaymentRequest constructor
==========================

::: {.section .multi-line-signature}
PaymentRequest(

1.  [List](../../dart-core/list-class)\<[Map](../../dart-core/map-class)\>
    methodData,
2.  [Map](../../dart-core/map-class) details,
3.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory PaymentRequest(List<Map> methodData, Map details, [Map? options]) {
  var methodData_1 = [];
  for (var i in methodData) {
    methodData_1.add(convertDartToNative_Dictionary(i));
  }
  if (options != null) {
    var details_1 = convertDartToNative_Dictionary(details);
    var options_2 = convertDartToNative_Dictionary(options);
    return PaymentRequest._create_1(methodData_1, details_1, options_2);
  }
  var details_1 = convertDartToNative_Dictionary(details);
  return PaymentRequest._create_2(methodData_1, details_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PaymentRequest/PaymentRequest.html>
:::
