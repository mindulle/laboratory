[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

connectNode method
==================

::: {.section .multi-line-signature}
void connectNode(

1.  [AudioNode](../audionode-class) destination,
2.  \[[int](../../dart-core/int-class) output = 0,
3.  [int](../../dart-core/int-class) input = 0\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void connectNode(AudioNode destination, [int output = 0, int input = 0]) {
  _connect(destination, output, input);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioNode/connectNode.html>
:::
