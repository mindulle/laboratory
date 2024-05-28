[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

allocate\<T extends NativeType\> method
=======================================

::: {.section .multi-line-signature}
[Pointer](../pointer-class)\<T\> allocate\<T extends NativeType\>(

1.  [int](../../dart-core/int-class) byteCount,
2.  {[int](../../dart-core/int-class)? alignment}

)
:::

Allocates `byteCount` bytes of memory on the native heap.

If `alignment` is provided, the allocated memory will be at least
aligned to `alignment` bytes.

To allocate a multiple of `sizeOf<T>()` bytes, call the allocator
directly as a function: `allocator<T>(count)` (see
[AllocatorAlloc.call](../allocatoralloc/call) for details).

``` {.language-dart data-language="dart"}
// This allocates two bytes. If you intended two Int32's, this is an
// error.
allocator.allocate<Int32>(2);

// This allocates eight bytes, which is enough space for two Int32's.
// However, this is not the idiomatic way.
allocator.allocate<Int32>(sizeOf<Int32>() * 2);

// The idiomatic way to allocate space for two Int32 is to call the
// allocator directly as a function.
allocator<Int32>(2);
```

Throws an [ArgumentError](../../dart-core/argumenterror-class) if the
number of bytes or alignment cannot be satisfied.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Pointer<T> allocate<T extends NativeType>(int byteCount, {int? alignment});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Allocator/allocate.html>
:::
