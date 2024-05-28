[dart:html](../../dart-html/dart-html-library){._links-link}

readValue method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) readValue()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future readValue() => promiseToFuture(JS("", "#.readValue()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BluetoothRemoteGattDescriptor/readValue.html>
:::
