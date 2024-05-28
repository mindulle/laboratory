[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

UnmodifiableByteDataView class
==============================

A read-only view of a [ByteData](bytedata-class).

Implemented types

:   -   [ByteData](bytedata-class)

Constructors
------------

[UnmodifiableByteDataView](unmodifiablebytedataview/unmodifiablebytedataview)([ByteData](bytedata-class)
data)

Properties {#instance-properties}
----------

[buffer](unmodifiablebytedataview/buffer) →
[ByteBuffer](bytebuffer-class)

::: {.features}
read-only, override
:::

Returns the byte buffer associated with this object.

[elementSizeInBytes](unmodifiablebytedataview/elementsizeinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Returns the number of bytes in the representation of each element in
this list.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[lengthInBytes](unmodifiablebytedataview/lengthinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Returns the length of this view, in bytes.

[offsetInBytes](unmodifiablebytedataview/offsetinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Returns the offset in bytes into the underlying byte buffer of this
view.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[getFloat32](unmodifiablebytedataview/getfloat32)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[double](../dart-core/double-class)

::: {.features}
override
:::

Returns the floating point number represented by the four bytes at the
specified `byteOffset` in this object, in IEEE 754 single-precision
binary floating-point format (binary32).

[getFloat64](unmodifiablebytedataview/getfloat64)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[double](../dart-core/double-class)

::: {.features}
override
:::

Returns the floating point number represented by the eight bytes at the
specified `byteOffset` in this object, in IEEE 754 double-precision
binary floating-point format (binary64).

[getInt16](unmodifiablebytedataview/getint16)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

Returns the (possibly negative) integer represented by the two bytes at
the specified `byteOffset` in this object, in two\'s complement binary
form.

[getInt32](unmodifiablebytedataview/getint32)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

Returns the (possibly negative) integer represented by the four bytes at
the specified `byteOffset` in this object, in two\'s complement binary
form.

[getInt64](unmodifiablebytedataview/getint64)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

Returns the (possibly negative) integer represented by the eight bytes
at the specified `byteOffset` in this object, in two\'s complement
binary form.

[getInt8](unmodifiablebytedataview/getint8)([int](../dart-core/int-class)
byteOffset) → [int](../dart-core/int-class)

::: {.features}
override
:::

Returns the (possibly negative) integer represented by the byte at the
specified `byteOffset` in this object, in two\'s complement binary
representation.

[getUint16](unmodifiablebytedataview/getuint16)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

Returns the positive integer represented by the two bytes starting at
the specified `byteOffset` in this object, in unsigned binary form.

[getUint32](unmodifiablebytedataview/getuint32)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

Returns the positive integer represented by the four bytes starting at
the specified `byteOffset` in this object, in unsigned binary form.

[getUint64](unmodifiablebytedataview/getuint64)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

Returns the positive integer represented by the eight bytes starting at
the specified `byteOffset` in this object, in unsigned binary form.

[getUint8](unmodifiablebytedataview/getuint8)([int](../dart-core/int-class)
byteOffset) → [int](../dart-core/int-class)

::: {.features}
override
:::

Returns the positive integer represented by the byte at the specified
`byteOffset` in this object, in unsigned binary form.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setFloat32](unmodifiablebytedataview/setfloat32)([int](../dart-core/int-class)
byteOffset, [double](../dart-core/double-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

::: {.features}
override
:::

Sets the four bytes starting at the specified `byteOffset` in this
object to the IEEE 754 single-precision binary floating-point (binary32)
representation of the specified `value`.

[setFloat64](unmodifiablebytedataview/setfloat64)([int](../dart-core/int-class)
byteOffset, [double](../dart-core/double-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

::: {.features}
override
:::

Sets the eight bytes starting at the specified `byteOffset` in this
object to the IEEE 754 double-precision binary floating-point (binary64)
representation of the specified `value`.

[setInt16](unmodifiablebytedataview/setint16)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

::: {.features}
override
:::

Sets the two bytes starting at the specified `byteOffset` in this object
to the two\'s complement binary representation of the specified `value`,
which must fit in two bytes.

[setInt32](unmodifiablebytedataview/setint32)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

::: {.features}
override
:::

Sets the four bytes starting at the specified `byteOffset` in this
object to the two\'s complement binary representation of the specified
`value`, which must fit in four bytes.

[setInt64](unmodifiablebytedataview/setint64)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

::: {.features}
override
:::

Sets the eight bytes starting at the specified `byteOffset` in this
object to the two\'s complement binary representation of the specified
`value`, which must fit in eight bytes.

[setInt8](unmodifiablebytedataview/setint8)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value) → void

::: {.features}
override
:::

Sets the byte at the specified `byteOffset` in this object to the two\'s
complement binary representation of the specified `value`, which must
fit in a single byte.

[setUint16](unmodifiablebytedataview/setuint16)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

::: {.features}
override
:::

Sets the two bytes starting at the specified `byteOffset` in this object
to the unsigned binary representation of the specified `value`, which
must fit in two bytes.

[setUint32](unmodifiablebytedataview/setuint32)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

::: {.features}
override
:::

Sets the four bytes starting at the specified `byteOffset` in this
object to the unsigned binary representation of the specified `value`,
which must fit in four bytes.

[setUint64](unmodifiablebytedataview/setuint64)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

::: {.features}
override
:::

Sets the eight bytes starting at the specified `byteOffset` in this
object to the unsigned binary representation of the specified `value`,
which must fit in eight bytes.

[setUint8](unmodifiablebytedataview/setuint8)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value) → void

::: {.features}
override
:::

Sets the byte at the specified `byteOffset` in this object to the
unsigned binary representation of the specified `value`, which must fit
in a single byte.

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
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableByteDataView-class.html>
:::
