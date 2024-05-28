[dart:html](../../dart-html/dart-html-library){._links-link}

setRemoteDescription method
===========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) setRemoteDescription(

1.  [Map](../../dart-core/map-class) description

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future setRemoteDescription(Map description) {
  var description_dict = convertDartToNative_Dictionary(description);
  return promiseToFuture(
      JS("", "#.setRemoteDescription(#)", this, description_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/setRemoteDescription.html>
:::
