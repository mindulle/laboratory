[dart:html](../../dart-html/dart-html-library){._links-link}

start method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) start(

1.  [Object](../../dart-core/object-class) stream

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future start(Object stream) =>
    promiseToFuture(JS("", "#.start(#)", this, stream));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/UnderlyingSourceBase/start.html>
:::
