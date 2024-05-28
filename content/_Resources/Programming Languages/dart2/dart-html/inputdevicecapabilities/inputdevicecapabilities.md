[dart:html](../../dart-html/dart-html-library){._links-link}

InputDeviceCapabilities constructor
===================================

::: {.section .multi-line-signature}
InputDeviceCapabilities(

1.  \[[Map](../../dart-core/map-class)? deviceInitDict\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory InputDeviceCapabilities([Map? deviceInitDict]) {
  if (deviceInitDict != null) {
    var deviceInitDict_1 = convertDartToNative_Dictionary(deviceInitDict);
    return InputDeviceCapabilities._create_1(deviceInitDict_1);
  }
  return InputDeviceCapabilities._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/InputDeviceCapabilities/InputDeviceCapabilities.html>
:::
