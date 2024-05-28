[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Allocator class
===============

Manages memory on the native heap.

When allocating memory, prefer calling this allocator directly as a
function (see [AllocatorAlloc.call](allocatoralloc/call) for details).

This interface provides only the [allocate](allocator/allocate) method
to allocate a block of bytes, and the [free](allocator/free) method to
release such a block again. Implementations only need to provide those
two methods. The [AllocatorAlloc.call](allocatoralloc/call) extension
method is defined in terms of those lower-level operations.

An example of an allocator wrapping another to count the number of
allocations:

``` {.language-dart data-language="dart"}
class CountingAllocator implements Allocator {
  final Allocator _wrappedAllocator;
  int _totalAllocations = 0;
  int _nonFreedAllocations = 0;

  CountingAllocator([Allocator? allocator])
      : _wrappedAllocator = allocator ?? calloc;

  int get totalAllocations => _totalAllocations;

  int get nonFreedAllocations => _nonFreedAllocations;

  @override
  Pointer<T> allocate<T extends NativeType>(int byteCount, {int? alignment}) {
    final result =
        _wrappedAllocator.allocate<T>(byteCount, alignment: alignment);
    _totalAllocations++;
    _nonFreedAllocations++;
    return result;
  }

  @override
  void free(Pointer<NativeType> pointer) {
    _wrappedAllocator.free(pointer);
    _nonFreedAllocations--;
  }
}
```

Available Extensions

:   -   [AllocatorAlloc](allocatoralloc)

Annotations

:   -   \@Since(\'2.12\')

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[allocate](allocator/allocate)\<T extends
[NativeType](nativetype-class)\>([int](../dart-core/int-class)
byteCount, {[int](../dart-core/int-class)? alignment}) →
[Pointer](pointer-class)\<T\>

Allocates `byteCount` bytes of memory on the native heap.

[free](allocator/free)([Pointer](pointer-class)\<[NativeType](nativetype-class)\>
pointer) → void

Releases memory allocated on the native heap.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Allocator-class.html>
:::
