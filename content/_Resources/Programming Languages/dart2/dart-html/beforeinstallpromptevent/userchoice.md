[dart:html](../../dart-html/dart-html-library){._links-link}

userChoice property
===================

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
dynamic\>?\> userChoice
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Map<String, dynamic>?> get userChoice =>
    promiseToFutureAsMap(JS("", "#.userChoice", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BeforeInstallPromptEvent/userChoice.html>
:::
