[dart:html](../../dart-html/dart-html-library){._links-link}

setSinkId method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) setSinkId(

1.  [String](../../dart-core/string-class) sinkId

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future setSinkId(String sinkId) =>
    promiseToFuture(JS("", "#.setSinkId(#)", this, sinkId));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaElement/setSinkId.html>
:::
