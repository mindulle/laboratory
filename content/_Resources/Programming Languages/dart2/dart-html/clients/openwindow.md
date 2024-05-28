[dart:html](../../dart-html/dart-html-library){._links-link}

openWindow method
=================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[WindowClient](../windowclient-class)\>
openWindow(

1.  [String](../../dart-core/string-class) url

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<WindowClient> openWindow(String url) => promiseToFuture<WindowClient>(
    JS("creates:WindowClient;", "#.openWindow(#)", this, url));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Clients/openWindow.html>
:::
