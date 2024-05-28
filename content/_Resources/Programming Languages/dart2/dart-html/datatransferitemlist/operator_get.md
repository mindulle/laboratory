[dart:html](../../dart-html/dart-html-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[DataTransferItem](../datatransferitem-class) operator \[\](

1.  [int](../../dart-core/int-class) index

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DataTransferItem operator [](int index) {
  return JS('DataTransferItem', '#[#]', this, index);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DataTransferItemList/operator_get.html>
:::
