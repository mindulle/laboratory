[dart:html](../../dart-html/dart-html-library){._links-link}

getStatusForPolicy method
=========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) getStatusForPolicy(

1.  [MediaKeysPolicy](../mediakeyspolicy-class) policy

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future getStatusForPolicy(MediaKeysPolicy policy) =>
    promiseToFuture(JS("", "#.getStatusForPolicy(#)", this, policy));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaKeys/getStatusForPolicy.html>
:::
