[dart:js](../../dart-js/dart-js-library){._links-link}

JsFunction.withThis constructor
===============================

::: {.section .multi-line-signature}
JsFunction.withThis(

1.  [Function](../../dart-core/function-class) f

)
:::

Returns a [JsFunction](../jsfunction-class) that captures its \'this\'
binding and calls `f` with the value of JavaScript `this` passed as the
first argument.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory JsFunction.withThis(Function f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsFunction/JsFunction.withThis.html>
:::
