dart:typed\_data library
========================

Lists that efficiently handle fixed sized data (for example, unsigned 8
byte integers) and SIMD numeric types.

To use this library in your code:

``` {.language-dart data-language="dart"}
import 'dart:typed_data';
```

Classes
-------

[ByteBuffer](bytebuffer-class)
:   A sequence of bytes underlying a typed data object.

[ByteData](bytedata-class)
:   A fixed-length, random-access sequence of bytes that also provides
    random and unaligned access to the fixed-width integers and floating
    point numbers represented by those bytes.

[BytesBuilder](bytesbuilder-class)
:   Builds a list of bytes, allowing bytes and lists of bytes to be
    added at the end.

[Endian](endian-class)
:   Describes endianness to be used when accessing or updating a
    sequence of bytes.

[Float32List](float32list-class)
:   A fixed-length list of IEEE 754 single-precision binary
    floating-point numbers that is viewable as a
    [TypedData](typeddata-class).

[Float32x4](float32x4-class)
:   Float32x4 immutable value type and operations.

[Float32x4List](float32x4list-class)
:   A fixed-length list of Float32x4 numbers that is viewable as a
    [TypedData](typeddata-class).

[Float64List](float64list-class)
:   A fixed-length list of IEEE 754 double-precision binary
    floating-point numbers that is viewable as a
    [TypedData](typeddata-class).

[Float64x2](float64x2-class)
:   Float64x2 immutable value type and operations.

[Float64x2List](float64x2list-class)
:   A fixed-length list of Float64x2 numbers that is viewable as a
    [TypedData](typeddata-class).

[Int16List](int16list-class)
:   A fixed-length list of 16-bit signed integers that is viewable as a
    [TypedData](typeddata-class).

[Int32List](int32list-class)
:   A fixed-length list of 32-bit signed integers that is viewable as a
    [TypedData](typeddata-class).

[Int32x4](int32x4-class)
:   Int32x4 and operations.

[Int32x4List](int32x4list-class)
:   A fixed-length list of Int32x4 numbers that is viewable as a
    [TypedData](typeddata-class).

[Int64List](int64list-class)
:   A fixed-length list of 64-bit signed integers that is viewable as a
    [TypedData](typeddata-class).

[Int8List](int8list-class)
:   A fixed-length list of 8-bit signed integers.

[TypedData](typeddata-class)
:   A typed view of a sequence of bytes.

[Uint16List](uint16list-class)
:   A fixed-length list of 16-bit unsigned integers that is viewable as
    a [TypedData](typeddata-class).

[Uint32List](uint32list-class)
:   A fixed-length list of 32-bit unsigned integers that is viewable as
    a [TypedData](typeddata-class).

[Uint64List](uint64list-class)
:   A fixed-length list of 64-bit unsigned integers that is viewable as
    a [TypedData](typeddata-class).

[Uint8ClampedList](uint8clampedlist-class)
:   A fixed-length list of 8-bit unsigned integers.

[Uint8List](uint8list-class)
:   A fixed-length list of 8-bit unsigned integers.

[UnmodifiableByteBufferView](unmodifiablebytebufferview-class)
:   A read-only view of a [ByteBuffer](bytebuffer-class).

[UnmodifiableByteDataView](unmodifiablebytedataview-class)
:   A read-only view of a [ByteData](bytedata-class).

[UnmodifiableFloat32ListView](unmodifiablefloat32listview-class)
:   View of a [Float32List](float32list-class) that disallows
    modification.

[UnmodifiableFloat32x4ListView](unmodifiablefloat32x4listview-class)
:   View of a [Float32x4List](float32x4list-class) that disallows
    modification.

[UnmodifiableFloat64ListView](unmodifiablefloat64listview-class)
:   View of a [Float64List](float64list-class) that disallows
    modification.

[UnmodifiableFloat64x2ListView](unmodifiablefloat64x2listview-class)
:   View of a [Float64x2List](float64x2list-class) that disallows
    modification.

[UnmodifiableInt16ListView](unmodifiableint16listview-class)
:   View of a [Int16List](int16list-class) that disallows modification.

[UnmodifiableInt32ListView](unmodifiableint32listview-class)
:   View of a [Int32List](int32list-class) that disallows modification.

[UnmodifiableInt32x4ListView](unmodifiableint32x4listview-class)
:   View of a [Int32x4List](int32x4list-class) that disallows
    modification.

[UnmodifiableInt64ListView](unmodifiableint64listview-class)
:   View of a [Int64List](int64list-class) that disallows modification.

[UnmodifiableInt8ListView](unmodifiableint8listview-class)
:   View of a [Int8List](int8list-class) that disallows modification.

[UnmodifiableUint16ListView](unmodifiableuint16listview-class)
:   View of a [Uint16List](uint16list-class) that disallows
    modification.

[UnmodifiableUint32ListView](unmodifiableuint32listview-class)
:   View of a [Uint32List](uint32list-class) that disallows
    modification.

[UnmodifiableUint64ListView](unmodifiableuint64listview-class)
:   View of a [Uint64List](uint64list-class) that disallows
    modification.

[UnmodifiableUint8ClampedListView](unmodifiableuint8clampedlistview-class)
:   View of a [Uint8ClampedList](uint8clampedlist-class) that disallows
    modification.

[UnmodifiableUint8ListView](unmodifiableuint8listview-class)
:   View of a [Uint8List](uint8list-class) that disallows modification.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/dart-typed_data-library.html>
:::
