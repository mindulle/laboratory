[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

length property
===============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) length

::: {.features}
override
:::
:::

The number of key/value pairs in the map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get length => JS('int', '#.size', this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioParamMap/length.html>
:::
