[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

connectParam method
===================

::: {.section .multi-line-signature}
void connectParam(

1.  [AudioParam](../audioparam-class) destination,
2.  \[[int](../../dart-core/int-class) output = 0\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void connectParam(AudioParam destination, [int output = 0]) {
  _connect(destination, output);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioNode/connectParam.html>
:::
