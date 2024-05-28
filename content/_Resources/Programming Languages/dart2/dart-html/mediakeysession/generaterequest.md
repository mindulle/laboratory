[dart:html](../../dart-html/dart-html-library){._links-link}

generateRequest method
======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) generateRequest(

1.  [String](../../dart-core/string-class) initDataType,
2.  dynamic initData

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future generateRequest(String initDataType, /*BufferSource*/ initData) =>
    promiseToFuture(
        JS("", "#.generateRequest(#, #)", this, initDataType, initData));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaKeySession/generateRequest.html>
:::
