[dart:html](../../dart-html/dart-html-library){._links-link}

setConfiguration method
=======================

::: {.section .multi-line-signature}
void setConfiguration(

1.  [Map](../../dart-core/map-class) configuration

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setConfiguration(Map configuration) {
  var configuration_1 = convertDartToNative_Dictionary(configuration);
  _setConfiguration_1(configuration_1);
  return;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/setConfiguration.html>
:::
