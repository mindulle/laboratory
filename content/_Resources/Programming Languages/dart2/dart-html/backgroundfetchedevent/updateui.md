[dart:html](../../dart-html/dart-html-library){._links-link}

updateUI method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) updateUI(

1.  [String](../../dart-core/string-class) title

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future updateUI(String title) =>
    promiseToFuture(JS("", "#.updateUI(#)", this, title));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BackgroundFetchedEvent/updateUI.html>
:::
