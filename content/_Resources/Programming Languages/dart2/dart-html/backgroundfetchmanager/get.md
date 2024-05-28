[dart:html](../../dart-html/dart-html-library){._links-link}

get method
==========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[BackgroundFetchRegistration](../backgroundfetchregistration-class)\>
get(

1.  [String](../../dart-core/string-class) id

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<BackgroundFetchRegistration> get(String id) =>
    promiseToFuture<BackgroundFetchRegistration>(
        JS("creates:BackgroundFetchRegistration;", "#.get(#)", this, id));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BackgroundFetchManager/get.html>
:::
