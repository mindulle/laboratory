[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

value property
==============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) value
:::

The 8-bit two\'s complement integer at [address](../pointer/address).

A Dart integer is truncated to 8 bits (as if by `.toSigned(8)`) before
being stored, and the 8-bit value is sign-extended when it is loaded.

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
<https://api.dart.dev/stable/2.18.5/dart-ffi/Int8Pointer/value.html>
:::
