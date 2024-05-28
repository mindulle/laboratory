[dart:html](../../dart-html/dart-html-library){._links-link}

play method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) play()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future play() => promiseToFuture(JS("", "#.play()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaElement/play.html>
:::
