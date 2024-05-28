[dart:html](../../dart-html/dart-html-library){._links-link}

requestMediaKeySystemAccess method
==================================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) requestMediaKeySystemAccess(

1.  [String](../../dart-core/string-class) keySystem,
2.  [List](../../dart-core/list-class)\<[Map](../../dart-core/map-class)\>
    supportedConfigurations

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future requestMediaKeySystemAccess(
        String keySystem, List<Map> supportedConfigurations) =>
    promiseToFuture(JS(
        "creates:MediaKeySystemAccess;",
        "#.requestMediaKeySystemAccess(#, #)",
        this,
        keySystem,
        supportedConfigurations));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Navigator/requestMediaKeySystemAccess.html>
:::
