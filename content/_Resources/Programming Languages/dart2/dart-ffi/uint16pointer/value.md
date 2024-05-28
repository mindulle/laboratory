[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

value property
==============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) value
:::

The 16-bit unsigned integer at [address](../pointer/address).

A Dart integer is truncated to 16 bits (as if by `.toUnsigned(16)`)
before being stored, and the 16-bit value is zero-extended when it is
loaded.

The [address](../pointer/address) must be 2-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int get value;
```

::: {#setter .section .multi-line-signature}
void value=([int](../../dart-core/int-class) value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void set value(int value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint16Pointer/value.html>
:::
