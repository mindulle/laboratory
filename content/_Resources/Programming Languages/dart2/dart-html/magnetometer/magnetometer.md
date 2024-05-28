[dart:html](../../dart-html/dart-html-library){._links-link}

Magnetometer constructor
========================

::: {.section .multi-line-signature}
Magnetometer(

1.  \[[Map](../../dart-core/map-class)? sensorOptions\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Magnetometer([Map? sensorOptions]) {
  if (sensorOptions != null) {
    var sensorOptions_1 = convertDartToNative_Dictionary(sensorOptions);
    return Magnetometer._create_1(sensorOptions_1);
  }
  return Magnetometer._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Magnetometer/Magnetometer.html>
:::
