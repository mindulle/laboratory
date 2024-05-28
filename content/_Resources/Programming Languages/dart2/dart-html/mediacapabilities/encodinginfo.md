[dart:html](../../dart-html/dart-html-library){._links-link}

encodingInfo method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[MediaCapabilitiesInfo](../mediacapabilitiesinfo-class)\>
encodingInfo(

1.  [Map](../../dart-core/map-class) configuration

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<MediaCapabilitiesInfo> encodingInfo(Map configuration) {
  var configuration_dict = convertDartToNative_Dictionary(configuration);
  return promiseToFuture<MediaCapabilitiesInfo>(JS(
      "creates:MediaCapabilitiesInfo;",
      "#.encodingInfo(#)",
      this,
      configuration_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaCapabilities/encodingInfo.html>
:::
