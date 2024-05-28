[dart:html](../../dart-html/dart-html-library){._links-link}

getAvailability method
======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[PresentationAvailability](../presentationavailability-class)\>
getAvailability()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<PresentationAvailability> getAvailability() =>
    promiseToFuture<PresentationAvailability>(
        JS("creates:PresentationAvailability;", "#.getAvailability()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PresentationRequest/getAvailability.html>
:::
