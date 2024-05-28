[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[Pointer](../pointer-class)\<T\> operator \[\](

1.  [int](../../dart-core/int-class) index

)
:::

Load a Dart value from this location offset by `index`.

A [Pointer](../pointer-class) is unboxed before being stored (as if by
`.address`), and the pointer is boxed (as if by `Pointer.fromAddress`)
when loaded.

On 32-bit platforms the [address](../pointer/address) must be 4-byte
aligned, and on 64-bit platforms the [address](../pointer/address) must
be 8-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Pointer<T> operator [](int index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/PointerPointer/operator_get.html>
:::
