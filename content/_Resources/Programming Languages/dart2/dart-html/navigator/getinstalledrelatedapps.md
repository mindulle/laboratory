[dart:html](../../dart-html/dart-html-library){._links-link}

getInstalledRelatedApps method
==============================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RelatedApplication](../relatedapplication-class)\>
getInstalledRelatedApps()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RelatedApplication> getInstalledRelatedApps() =>
    promiseToFuture<RelatedApplication>(JS(
        "creates:RelatedApplication;", "#.getInstalledRelatedApps()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Navigator/getInstalledRelatedApps.html>
:::
