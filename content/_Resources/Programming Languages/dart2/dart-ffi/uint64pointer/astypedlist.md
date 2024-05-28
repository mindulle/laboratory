[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

asTypedList method
==================

::: {.section .multi-line-signature}
[Uint64List](../../dart-typed_data/uint64list-class) asTypedList(

1.  [int](../../dart-core/int-class) length

)
:::

Creates a typed list view backed by memory in the address space.

The returned view will allow access to the memory range from
[address](../pointer/address) to `address + 8 * length`.

The user has to ensure the memory range is accessible while using the
returned list.

The [address](../pointer/address) must be 8-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Uint64List asTypedList(int length);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint64Pointer/asTypedList.html>
:::
