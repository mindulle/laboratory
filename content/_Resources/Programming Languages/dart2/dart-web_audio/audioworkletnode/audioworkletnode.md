[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

AudioWorkletNode constructor
============================

::: {.section .multi-line-signature}
AudioWorkletNode(

1.  [BaseAudioContext](../baseaudiocontext-class) context,
2.  [String](../../dart-core/string-class) name,
3.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory AudioWorkletNode(BaseAudioContext context, String name,
    [Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return AudioWorkletNode._create_1(context, name, options_1);
  }
  return AudioWorkletNode._create_2(context, name);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioWorkletNode/AudioWorkletNode.html>
:::
