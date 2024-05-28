[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

call\<T extends NativeType\> method
===================================

::: {.section .multi-line-signature}
[Pointer](../pointer-class)\<T\> call\<T extends NativeType\>(

1.  \[[int](../../dart-core/int-class) count = 1\]

)
:::

Allocates `sizeOf<T>() * count` bytes of memory using
[allocate](../allocator/allocate).

``` {.language-dart data-language="dart"}
// This allocates eight bytes, which is enough space for two Int32's.
allocator<Int32>(2);
```

This extension method must be invoked with a compile-time constant `T`.

To allocate a specific number of bytes, not just a multiple of
`sizeOf<T>()`, use [allocate](../allocator/allocate). To allocate with a
non constant `T`, use [allocate](../allocator/allocate). Prefer
[call](call) for normal use, and use [allocate](../allocator/allocate)
for implementing an [Allocator](../allocator-class) in terms of other
allocators.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Pointer<T> call<T extends NativeType>([int count = 1]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/AllocatorAlloc/call.html>
:::
