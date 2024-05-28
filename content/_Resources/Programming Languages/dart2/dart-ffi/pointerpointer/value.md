[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

value property
==============

::: {#getter .section .multi-line-signature}
[Pointer](../pointer-class)\<T\> value
:::

The pointer at [address](../pointer/address).

A [Pointer](../pointer-class) is unboxed before being stored (as if by
`.address`), and the pointer is boxed (as if by `Pointer.fromAddress`)
when loaded.

On 32-bit platforms the [address](../pointer/address) must be 4-byte
aligned, and on 64-bit platforms the [address](../pointer/address) must
be 8-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Pointer<T> get value;
```

::: {#setter .section .multi-line-signature}
void value=([Pointer](../pointer-class)\<T\> value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void set value(Pointer<T> value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/PointerPointer/value.html>
:::
