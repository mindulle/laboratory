[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

resume method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) resume()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future resume() => promiseToFuture(JS("", "#.resume()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/BaseAudioContext/resume.html>
:::
