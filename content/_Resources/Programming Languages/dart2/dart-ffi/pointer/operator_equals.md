[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) operator ==(

1.  [Object](../../dart-core/object-class) other

)

::: {.features}
override
:::
:::

Equality for Pointers only depends on their address.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other) {
  if (other is! Pointer) return false;
  Pointer otherPointer = other;
  return address == otherPointer.address;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Pointer/operator_equals.html>
:::
