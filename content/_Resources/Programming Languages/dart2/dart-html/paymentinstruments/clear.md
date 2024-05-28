[dart:html](../../dart-html/dart-html-library){._links-link}

clear method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) clear()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future clear() => promiseToFuture(JS("", "#.clear()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PaymentInstruments/clear.html>
:::
