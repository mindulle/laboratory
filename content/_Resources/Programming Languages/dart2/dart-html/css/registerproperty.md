[dart:html](../../dart-html/dart-html-library){._links-link}

registerProperty method
=======================

::: {.section .multi-line-signature}
void registerProperty(

1.  [Map](../../dart-core/map-class) descriptor

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void registerProperty(Map descriptor) {
  var descriptor_1 = convertDartToNative_Dictionary(descriptor);
  _registerProperty_1(descriptor_1);
  return;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Css/registerProperty.html>
:::
