[dart:js](../../dart-js/dart-js-library){._links-link}

callMethod method
=================

::: {.section .multi-line-signature}
dynamic callMethod(

1.  [Object](../../dart-core/object-class) method,
2.  \[[List](../../dart-core/list-class)? args\]

)
:::

Calls `method` on the JavaScript object with the arguments `args` and
returns the result.

The type of `method` must be either
[String](../../dart-core/string-class) or
[num](../../dart-core/num-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external dynamic callMethod(Object method, [List? args]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsObject/callMethod.html>
:::
