[dart:core](../../dart-core/dart-core-library){._links-link}

operator \[\]= method
=====================

::: {.section .multi-line-signature}
void operator \[\]=(

1.  [Object](../object-class) object,
2.  T? value

)
:::

Sets this [Expando](../expando-class)\'s property value on the given
object to `value`.

Properties can effectively be removed again by setting their value to
`null`.

The object must not be a number, a string, a boolean, `null`, a
`dart:ffi` pointer, a `dart:ffi` struct, or a `dart:ffi` union.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void operator []=(Object object, T? value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Expando/operator_put.html>
:::
