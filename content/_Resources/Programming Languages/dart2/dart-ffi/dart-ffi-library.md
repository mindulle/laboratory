dart:ffi library
================

Foreign Function Interface for interoperability with the C programming
language.

For further details, please see: <https://dart.dev/server/c-interop>.

Classes
-------

[Abi](abi-class)
:   An application binary interface (ABI).

[AbiSpecificInteger](abispecificinteger-class)
:   The supertype of all [Abi](abi-class)-specific integer types.

[AbiSpecificIntegerMapping](abispecificintegermapping-class)
:   Mapping for a subtype of
    [AbiSpecificInteger](abispecificinteger-class).

[Allocator](allocator-class)
:   Manages memory on the native heap.

[Array](array-class)\<T extends [NativeType](nativetype-class)\>
:   A fixed-sized array of `T`s.

[Bool](bool-class)
:   Represents a native bool in C.

[Char](char-class)
:   The C `char` type.

[Dart\_CObject](dart_cobject-class)
:   Opaque, not exposing it\'s members.

[DartRepresentationOf](dartrepresentationof-class)\
[Double](double-class)
:   Represents a native 64 bit double in C.

[DynamicLibrary](dynamiclibrary-class)
:   A dynamically loaded native library.

[FfiNative](ffinative-class)\<T\>
:   Annotation to be used for marking an external function as FFI
    native.

[Finalizable](finalizable-class)
:   Marker interface for objects which should not be finalized too soon.

[Float](float-class)
:   Represents a native 32 bit float in C.

[Handle](handle-class)
:   Represents `Dart_Handle` in C.

[Int](int-class)
:   The C `int` type.

[Int16](int16-class)
:   Represents a native signed 16 bit integer in C.

[Int32](int32-class)
:   Represents a native signed 32 bit integer in C.

[Int64](int64-class)
:   Represents a native signed 64 bit integer in C.

[Int8](int8-class)
:   Represents a native signed 8 bit integer in C.

[IntPtr](intptr-class)
:   The C `intptr_t` type.

[Long](long-class)
:   The C `long int`, aka. `long`, type.

[LongLong](longlong-class)
:   The C `long long` type.

[NativeApi](nativeapi-class)
:   Utilities for accessing the Dart VM API from Dart code or from C
    code via `dart_api_dl.h`.

[NativeFinalizer](nativefinalizer-class)
:   A native finalizer which can be attached to Dart objects.

[NativeFunction](nativefunction-class)\<T extends [Function](../dart-core/function-class)\>
:   Represents a function type in C.

[NativeType](nativetype-class)
:   [NativeType](nativetype-class)\'s subtypes represent a native type
    in C.

[Opaque](opaque-class)
:   [Opaque](opaque-class)\'s subtypes represent opaque types in C.

[Packed](packed-class)
:   Annotation to specify on `Struct` subtypes to indicate that its
    members need to be packed.

[Pointer](pointer-class)\<T extends [NativeType](nativetype-class)\>
:   Represents a pointer into the native C memory. Cannot be extended.

[Short](short-class)
:   The C `short` type.

[SignedChar](signedchar-class)
:   The C `signed char` type.

[Size](size-class)
:   The C `size_t` type.

[Struct](struct-class)
:   The supertype of all FFI struct types.

[Uint16](uint16-class)
:   Represents a native unsigned 16 bit integer in C.

[Uint32](uint32-class)
:   Represents a native unsigned 32 bit integer in C.

[Uint64](uint64-class)
:   Represents a native unsigned 64 bit integer in C.

[Uint8](uint8-class)
:   Represents a native unsigned 8 bit integer in C.

[UintPtr](uintptr-class)
:   The C `uintptr_t` type.

[Union](union-class)
:   The supertype of all FFI union types.

[UnsignedChar](unsignedchar-class)
:   The C `unsigned char` type.

[UnsignedInt](unsignedint-class)
:   The C `unsigned int` type.

[UnsignedLong](unsignedlong-class)
:   The C `unsigned long int`, aka. `unsigned long`, type.

[UnsignedLongLong](unsignedlonglong-class)
:   The C `unsigned long long` type.

[UnsignedShort](unsignedshort-class)
:   The C `unsigned short` type.

[Unsized](unsized-class)\
[Void](void-class)
:   Represents a void type in C.

[WChar](wchar-class)
:   The C `wchar_t` type.

Extensions
----------

[AbiSpecificIntegerArray](abispecificintegerarray)
:   Bounds checking indexing methods on [Array](array-class)s of
    [AbiSpecificInteger](abispecificinteger-class).

[AbiSpecificIntegerPointer](abispecificintegerpointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [AbiSpecificInteger](abispecificinteger-class).

[AllocatorAlloc](allocatoralloc)
:   Extension on [Allocator](allocator-class) to provide allocation with
    [NativeType](nativetype-class).

[ArrayArray](arrayarray)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Array](array-class).

[BoolArray](boolarray)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Bool](bool-class).

[BoolPointer](boolpointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Bool](bool-class).

[DoubleArray](doublearray)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Double](double-class).

[DoublePointer](doublepointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Double](double-class).

[DynamicLibraryExtension](dynamiclibraryextension)
:   Method which must not be invoked dynamically.

[FloatArray](floatarray)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Float](float-class).

[FloatPointer](floatpointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Float](float-class).

[Int16Array](int16array)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Int16](int16-class).

[Int16Pointer](int16pointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Int16](int16-class).

[Int32Array](int32array)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Int32](int32-class).

[Int32Pointer](int32pointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Int32](int32-class).

[Int64Array](int64array)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Int64](int64-class).

[Int64Pointer](int64pointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Int64](int64-class).

[Int8Array](int8array)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Int8](int8-class).

[Int8Pointer](int8pointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Int8](int8-class).

[NativeFunctionPointer](nativefunctionpointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [NativeFunction](nativefunction-class).

[NativePort](nativeport)
:   Extension to retrieve the native `Dart_Port` from a
    [SendPort](../dart-isolate/sendport-class).

[PointerArray](pointerarray)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Pointer](pointer-class).

[PointerPointer](pointerpointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Pointer](pointer-class).

[StructArray](structarray)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Struct](struct-class).

[StructPointer](structpointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Struct](struct-class).

[Uint16Array](uint16array)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Uint16](uint16-class).

[Uint16Pointer](uint16pointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Uint16](uint16-class).

[Uint32Array](uint32array)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Uint32](uint32-class).

[Uint32Pointer](uint32pointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Uint32](uint32-class).

[Uint64Array](uint64array)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Uint64](uint64-class).

[Uint64Pointer](uint64pointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Uint64](uint64-class).

[Uint8Array](uint8array)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Uint8](uint8-class).

[Uint8Pointer](uint8pointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Uint8](uint8-class).

[UnionArray](unionarray)
:   Bounds checking indexing methods on [Array](array-class)s of
    [Union](union-class).

[UnionPointer](unionpointer)
:   Extension on [Pointer](pointer-class) specialized for the type
    argument [Union](union-class).

Constants
---------

[unsized](unsized-constant) → const [Unsized](unsized-class)
:   This [NativeType](nativetype-class) does not have predefined size.
    <div>

    `const Unsized()`

    </div>

Properties
----------

[nullptr](nullptr) → [Pointer](pointer-class)\<Never\>

::: {.features}
final
:::

Represents a pointer into the native C memory corresponding to \'NULL\',
e.g. a pointer with address 0.

Functions
---------

[sizeOf](sizeof)\<T extends [NativeType](nativetype-class)\>() → [int](../dart-core/int-class)
:   Number of bytes used by native type T.

Typedefs
--------

[Dart\_NativeMessageHandler](dart_nativemessagehandler) = [Void](void-class) Function([Int64](int64-class), [Pointer](pointer-class)\<[Dart\_CObject](dart_cobject-class)\>)\
[NativeFinalizerFunction](nativefinalizerfunction) = [NativeFunction](nativefunction-class)\<[Void](void-class) Function([Pointer](pointer-class)\<[Void](void-class)\> token)\>
:   The native function type for
    [NativeFinalizer](nativefinalizer-class)s.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/dart-ffi-library.html>
:::
