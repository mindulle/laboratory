[dart:js](../../dart-js/dart-js-library){._links-link}

JsObject constructor
====================

::: {.section .multi-line-signature}
JsObject(

1.  [JsFunction](../jsfunction-class) constructor,
2.  \[[List](../../dart-core/list-class)? arguments\]

)
:::

Constructs a JavaScript object from its native `constructor` and returns
a proxy to it.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory JsObject(JsFunction constructor, [List? arguments]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsObject/JsObject.html>
:::
