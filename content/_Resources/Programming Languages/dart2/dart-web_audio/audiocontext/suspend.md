[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

suspend method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) suspend()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future suspend() => promiseToFuture(JS("", "#.suspend()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioContext/suspend.html>
:::
