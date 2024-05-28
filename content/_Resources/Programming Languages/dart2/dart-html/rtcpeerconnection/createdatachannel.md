[dart:html](../../dart-html/dart-html-library){._links-link}

createDataChannel method
========================

::: {.section .multi-line-signature}
[RtcDataChannel](../rtcdatachannel-class) createDataChannel(

1.  [String](../../dart-core/string-class) label,
2.  \[[Map](../../dart-core/map-class)? dataChannelDict\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RtcDataChannel createDataChannel(String label, [Map? dataChannelDict]) {
  if (dataChannelDict != null) {
    var dataChannelDict_1 = convertDartToNative_Dictionary(dataChannelDict);
    return _createDataChannel_1(label, dataChannelDict_1);
  }
  return _createDataChannel_2(label);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/createDataChannel.html>
:::
