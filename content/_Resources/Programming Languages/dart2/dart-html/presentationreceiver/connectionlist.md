[dart:html](../../dart-html/dart-html-library){._links-link}

connectionList property
=======================

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class)\<[PresentationConnectionList](../presentationconnectionlist-class)\>
connectionList
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<PresentationConnectionList> get connectionList =>
    promiseToFuture<PresentationConnectionList>(
        JS("creates:PresentationConnectionList;", "#.connectionList", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PresentationReceiver/connectionList.html>
:::
