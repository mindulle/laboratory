[dart:js\_util](../dart-js_util/dart-js_util-library){._links-link}

dartify function
================

::: {.section .multi-line-signature}
[Object](../dart-core/object-class)? dartify(

1.  [Object](../dart-core/object-class)? o

)
:::

Effectively the inverse of [jsify](jsify), [dartify](dartify) Takes a
JavaScript object, and converts it to a Dart based object. Only JS
primitives, arrays, or \'map\' like JS objects are supported.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Object? dartify(Object? o);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js_util/dartify.html>
:::
