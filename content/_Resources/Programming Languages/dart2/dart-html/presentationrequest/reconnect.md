[dart:html](../../dart-html/dart-html-library){._links-link}

reconnect method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[PresentationConnection](../presentationconnection-class)\>
reconnect(

1.  [String](../../dart-core/string-class) id

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<PresentationConnection> reconnect(String id) =>
    promiseToFuture<PresentationConnection>(
        JS("creates:PresentationConnection;", "#.reconnect(#)", this, id));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PresentationRequest/reconnect.html>
:::
