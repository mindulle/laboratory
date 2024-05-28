[dart:html](../../dart-html/dart-html-library){._links-link}

loaded property
===============

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FontFace](../fontface-class)\>
loaded
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<FontFace> get loaded =>
    promiseToFuture<FontFace>(JS("creates:FontFace;", "#.loaded", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FontFace/loaded.html>
:::
