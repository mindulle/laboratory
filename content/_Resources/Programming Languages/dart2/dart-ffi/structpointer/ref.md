[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

ref property
============

::: {#getter .section .multi-line-signature}
T ref
:::

A Dart view of the struct referenced by this pointer.

Reading [ref](ref) creates a reference accessing the fields of this
struct backed by native memory at [address](../pointer/address). The
[address](../pointer/address) must be aligned according to the struct
alignment rules of the platform.

Assigning to [ref](ref) copies contents of the struct into the native
memory starting at [address](../pointer/address).

This extension method must be invoked on a receiver of type `Pointer<T>`
where `T` is a compile-time constant type.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external T get ref;
```

::: {#setter .section .multi-line-signature}
void ref=(T value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external set ref(T value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/StructPointer/ref.html>
:::
