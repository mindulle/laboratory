[dart:html](../../dart-html/dart-html-library){._links-link}

register method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) register(

1.  [String](../../dart-core/string-class) tag

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future register(String tag) =>
    promiseToFuture(JS("", "#.register(#)", this, tag));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SyncManager/register.html>
:::
