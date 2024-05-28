[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

ByteBuffer class
================

A sequence of bytes underlying a typed data object.

Used to process large quantities of binary or numerical data more
efficiently using a typed view.

Implementers

:   -   [UnmodifiableByteBufferView](unmodifiablebytebufferview-class)

Constructors
------------

[ByteBuffer](bytebuffer/bytebuffer)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[lengthInBytes](bytebuffer/lengthinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

Returns the length of this byte buffer, in bytes.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[asByteData](bytebuffer/asbytedata)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[ByteData](bytedata-class)

Creates a [ByteData](bytedata-class) *view* of a region of this byte
buffer.

[asFloat32List](bytebuffer/asfloat32list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Float32List](float32list-class)

Creates a [Float32List](float32list-class) *view* of a region of this
byte buffer.

[asFloat32x4List](bytebuffer/asfloat32x4list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Float32x4List](float32x4list-class)

Creates a [Float32x4List](float32x4list-class) *view* of a region of
this byte buffer.

[asFloat64List](bytebuffer/asfloat64list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Float64List](float64list-class)

Creates a [Float64List](float64list-class) *view* of a region of this
byte buffer.

[asFloat64x2List](bytebuffer/asfloat64x2list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Float64x2List](float64x2list-class)

Creates a [Float64x2List](float64x2list-class) *view* of a region of
this byte buffer.

[asInt16List](bytebuffer/asint16list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Int16List](int16list-class)

Creates a [Int16List](int16list-class) *view* of a region of this byte
buffer.

[asInt32List](bytebuffer/asint32list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Int32List](int32list-class)

Creates a [Int32List](int32list-class) *view* of a region of this byte
buffer.

[asInt32x4List](bytebuffer/asint32x4list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Int32x4List](int32x4list-class)

Creates a [Int32x4List](int32x4list-class) *view* of a region of this
byte buffer.

[asInt64List](bytebuffer/asint64list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Int64List](int64list-class)

Creates a [Int64List](int64list-class) *view* of a region of this byte
buffer.

[asInt8List](bytebuffer/asint8list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Int8List](int8list-class)

Creates a [Int8List](int8list-class) *view* of a region of this byte
buffer.

[asUint16List](bytebuffer/asuint16list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Uint16List](uint16list-class)

Creates a [Uint16List](uint16list-class) *view* of a region of this byte
buffer.

[asUint32List](bytebuffer/asuint32list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Uint32List](uint32list-class)

Creates a [Uint32List](uint32list-class) *view* of a region of this byte
buffer.

[asUint64List](bytebuffer/asuint64list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Uint64List](uint64list-class)

Creates a [Uint64List](uint64list-class) *view* of a region of this byte
buffer.

[asUint8ClampedList](bytebuffer/asuint8clampedlist)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Uint8ClampedList](uint8clampedlist-class)

Creates a [Uint8ClampedList](uint8clampedlist-class) *view* of a region
of this byte buffer.

[asUint8List](bytebuffer/asuint8list)(\[[int](../dart-core/int-class)
offsetInBytes = 0, [int](../dart-core/int-class)? length\]) →
[Uint8List](uint8list-class)

Creates a [Uint8List](uint8list-class) *view* of a region of this byte
buffer.

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
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteBuffer-class.html>
:::
