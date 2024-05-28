[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

DelayNode constructor
=====================

::: {.section .multi-line-signature}
DelayNode(

1.  [BaseAudioContext](../baseaudiocontext-class) context,
2.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DelayNode(BaseAudioContext context, [Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return DelayNode._create_1(context, options_1);
  }
  return DelayNode._create_2(context);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/DelayNode/DelayNode.html>
:::
