[dart:html](../../dart-html/dart-html-library){._links-link}

whenDefined method
==================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) whenDefined(

1.  [String](../../dart-core/string-class) name

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future whenDefined(String name) =>
    promiseToFuture(JS("", "#.whenDefined(#)", this, name));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CustomElementRegistry/whenDefined.html>
:::
