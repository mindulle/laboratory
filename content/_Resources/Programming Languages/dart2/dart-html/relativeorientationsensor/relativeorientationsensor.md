[dart:html](../../dart-html/dart-html-library){._links-link}

RelativeOrientationSensor constructor
=====================================

::: {.section .multi-line-signature}
RelativeOrientationSensor(

1.  \[[Map](../../dart-core/map-class)? sensorOptions\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory RelativeOrientationSensor([Map? sensorOptions]) {
  if (sensorOptions != null) {
    var sensorOptions_1 = convertDartToNative_Dictionary(sensorOptions);
    return RelativeOrientationSensor._create_1(sensorOptions_1);
  }
  return RelativeOrientationSensor._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RelativeOrientationSensor/RelativeOrientationSensor.html>
:::
