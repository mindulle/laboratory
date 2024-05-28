[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

AllocatorAlloc extension
========================

Extension on [Allocator](allocator-class) to provide allocation with
[NativeType](nativetype-class).

on

:   -   [Allocator](allocator-class)

Annotations

-   \@Since(\'2.12\')

Methods {#instance-methods}
-------

[call](allocatoralloc/call)\<T extends [NativeType](nativetype-class)\>(\[[int](../dart-core/int-class) count = 1\]) → [Pointer](pointer-class)\<T\>
:   Allocates `sizeOf<T>() * count` bytes of memory using
    [allocate](allocator/allocate).

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/AllocatorAlloc.html>
:::
