[dart:js\_util](../dart-js_util/dart-js_util-library){._links-link}

isJavaScriptArray function
==========================

::: {.section .multi-line-signature}
[bool](../dart-core/bool-class) isJavaScriptArray(

1.  dynamic value

)
:::

Returns `true` if a given object is a JavaScript array.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool isJavaScriptArray(value) => instanceOfString(value, 'Array');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js_util/isJavaScriptArray.html>
:::
