[dart:html](../../dart-html/dart-html-library){._links-link}

writeValue method
=================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) writeValue(

1.  dynamic value

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future writeValue(/*BufferSource*/ value) =>
    promiseToFuture(JS("", "#.writeValue(#)", this, value));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BluetoothRemoteGattDescriptor/writeValue.html>
:::
