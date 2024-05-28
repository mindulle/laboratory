[dart:core](../../dart-core/dart-core-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
T? operator \[\](

1.  [Object](../object-class) object

)
:::

Gets the value of this [Expando](../expando-class)\'s property on the
given object.

If the object hasn\'t been expanded, the result is the `null` value.

The object must not be a number, a string, a boolean, `null`, a
`dart:ffi` pointer, a `dart:ffi` struct, or a `dart:ffi` union.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external T? operator [](Object object);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Expando/operator_get.html>
:::
