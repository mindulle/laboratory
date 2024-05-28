[dart:html](../../dart-html/dart-html-library){._links-link}

requestPresent method
=====================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) requestPresent(

1.  [List](../../dart-core/list-class)\<[Map](../../dart-core/map-class)\>
    layers

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future requestPresent(List<Map> layers) =>
    promiseToFuture(JS("", "#.requestPresent(#)", this, layers));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/VRDisplay/requestPresent.html>
:::
