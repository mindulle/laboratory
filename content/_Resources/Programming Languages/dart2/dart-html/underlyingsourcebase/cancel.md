[dart:html](../../dart-html/dart-html-library){._links-link}

cancel method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) cancel(

1.  [Object](../../dart-core/object-class)? reason

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future cancel(Object? reason) =>
    promiseToFuture(JS("", "#.cancel(#)", this, reason));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/UnderlyingSourceBase/cancel.html>
:::
