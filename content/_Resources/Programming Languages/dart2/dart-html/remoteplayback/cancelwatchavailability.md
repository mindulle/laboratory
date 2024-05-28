[dart:html](../../dart-html/dart-html-library){._links-link}

cancelWatchAvailability method
==============================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) cancelWatchAvailability(

1.  \[[int](../../dart-core/int-class)? id\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future cancelWatchAvailability([int? id]) =>
    promiseToFuture(JS("", "#.cancelWatchAvailability(#)", this, id));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RemotePlayback/cancelWatchAvailability.html>
:::
