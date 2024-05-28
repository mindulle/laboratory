[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Pointer\<T extends NativeType\> class
=====================================

Represents a pointer into the native C memory. Cannot be extended.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   Pointer

Available Extensions

:   -   [AbiSpecificIntegerPointer](abispecificintegerpointer)
    -   [BoolPointer](boolpointer)
    -   [DoublePointer](doublepointer)
    -   [FloatPointer](floatpointer)
    -   [Int8Pointer](int8pointer)
    -   [Int16Pointer](int16pointer)
    -   [Int32Pointer](int32pointer)
    -   [Int64Pointer](int64pointer)
    -   [NativeFunctionPointer](nativefunctionpointer)
    -   [PointerPointer](pointerpointer)
    -   [StructPointer](structpointer)
    -   [Uint8Pointer](uint8pointer)
    -   [Uint16Pointer](uint16pointer)
    -   [Uint32Pointer](uint32pointer)
    -   [Uint64Pointer](uint64pointer)
    -   [UnionPointer](unionpointer)

Constructors
------------

[Pointer.fromAddress](pointer/pointer.fromaddress)([int](../dart-core/int-class)
ptr)

::: {.constructor-modifier .features}
factory
:::

Construction from raw integer.

Properties {#instance-properties}
----------

[address](pointer/address) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Access to the raw pointer value. On 32-bit systems, the upper 32-bits of
the result are 0.

[hashCode](pointer/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

The hash code for a Pointer only depends on its address.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[cast](pointer/cast)\<U extends [NativeType](nativetype-class)\>() →
[Pointer](pointer-class)\<U\>

Cast Pointer to a Pointer.

[elementAt](pointer/elementat)([int](../dart-core/int-class) index) →
[Pointer](pointer-class)\<T\>

Pointer arithmetic (takes element size into account).

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
==](pointer/operator_equals)([Object](../dart-core/object-class) other)
→ [bool](../dart-core/bool-class)

::: {.features}
override
:::

Equality for Pointers only depends on their address.

Static Methods
--------------

[fromFunction](pointer/fromfunction)\<T extends [Function](../dart-core/function-class)\>([Function](../dart-core/function-class) f, \[[Object](../dart-core/object-class)? exceptionalReturn\]) → [Pointer](pointer-class)\<[NativeFunction](nativefunction-class)\<T\>\>
:   Convert Dart function to a C function pointer, automatically
    marshalling the arguments and return value

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Pointer-class.html>
:::
