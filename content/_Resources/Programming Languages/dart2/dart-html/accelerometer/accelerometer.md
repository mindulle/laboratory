[dart:html](../../dart-html/dart-html-library){._links-link}

Accelerometer constructor
=========================

::: {.section .multi-line-signature}
Accelerometer(

1.  \[[Map](../../dart-core/map-class)? sensorOptions\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Accelerometer([Map? sensorOptions]) {
  if (sensorOptions != null) {
    var sensorOptions_1 = convertDartToNative_Dictionary(sensorOptions);
    return Accelerometer._create_1(sensorOptions_1);
  }
  return Accelerometer._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Accelerometer/Accelerometer.html>
:::
