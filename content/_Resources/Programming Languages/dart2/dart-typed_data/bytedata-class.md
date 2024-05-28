[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

ByteData class
==============

A fixed-length, random-access sequence of bytes that also provides
random and unaligned access to the fixed-width integers and floating
point numbers represented by those bytes.

`ByteData` may be used to pack and unpack data from external sources
(such as networks or files systems), and to process large quantities of
numerical data more efficiently than would be possible with ordinary
[List](../dart-core/list-class) implementations. `ByteData` can save
space, by eliminating the need for object headers, and time, by
eliminating the need for data copies.

If data comes in as bytes, they can be converted to `ByteData` by
sharing the same buffer.

``` {.language-dart data-language="dart"}
Uint8List bytes = ...;
var blob = ByteData.sublistView(bytes);
if (blob.getUint32(0, Endian.little) == 0x04034b50) { // Zip file marker
  ...
}
```

Finally, `ByteData` may be used to intentionally reinterpret the bytes
representing one arithmetic type as another. For example this code
fragment determine what 32-bit signed integer is represented by the
bytes of a 32-bit floating point number (both stored as big endian):

``` {.language-dart data-language="dart"}
var bdata = ByteData(8);
bdata.setFloat32(0, 3.04);
int huh = bdata.getInt32(0); // 0x40428f5c
```

Implemented types

:   -   [TypedData](typeddata-class)

Implementers

:   -   [UnmodifiableByteDataView](unmodifiablebytedataview-class)

Constructors
------------

[ByteData](bytedata/bytedata)([int](../dart-core/int-class) length)

::: {.constructor-modifier .features}
factory
:::

Creates a [ByteData](bytedata-class) of the specified length (in
elements), all of whose bytes are initially zero.

[ByteData.sublistView](bytedata/bytedata.sublistview)([TypedData](typeddata-class)
data, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\])

::: {.constructor-modifier .features}
factory
:::

Creates a [ByteData](bytedata-class) view on a range of elements of
`data`.

[ByteData.view](bytedata/bytedata.view)([ByteBuffer](bytebuffer-class)
buffer, \[[int](../dart-core/int-class) offsetInBytes = 0,
[int](../dart-core/int-class)? length\])

::: {.constructor-modifier .features}
factory
:::

Creates an [ByteData](bytedata-class) *view* of the specified region in
`buffer`.

Properties {#instance-properties}
----------

[buffer](typeddata/buffer) → [ByteBuffer](bytebuffer-class)

::: {.features}
read-only, inherited
:::

Returns the byte buffer associated with this object.

[elementSizeInBytes](typeddata/elementsizeinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

Returns the number of bytes in the representation of each element in
this list.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[lengthInBytes](typeddata/lengthinbytes) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

Returns the length of this view, in bytes.

[offsetInBytes](typeddata/offsetinbytes) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
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

[getFloat32](bytedata/getfloat32)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[double](../dart-core/double-class)

Returns the floating point number represented by the four bytes at the
specified `byteOffset` in this object, in IEEE 754 single-precision
binary floating-point format (binary32).

[getFloat64](bytedata/getfloat64)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[double](../dart-core/double-class)

Returns the floating point number represented by the eight bytes at the
specified `byteOffset` in this object, in IEEE 754 double-precision
binary floating-point format (binary64).

[getInt16](bytedata/getint16)([int](../dart-core/int-class) byteOffset,
\[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

Returns the (possibly negative) integer represented by the two bytes at
the specified `byteOffset` in this object, in two\'s complement binary
form.

[getInt32](bytedata/getint32)([int](../dart-core/int-class) byteOffset,
\[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

Returns the (possibly negative) integer represented by the four bytes at
the specified `byteOffset` in this object, in two\'s complement binary
form.

[getInt64](bytedata/getint64)([int](../dart-core/int-class) byteOffset,
\[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

Returns the (possibly negative) integer represented by the eight bytes
at the specified `byteOffset` in this object, in two\'s complement
binary form.

[getInt8](bytedata/getint8)([int](../dart-core/int-class) byteOffset) →
[int](../dart-core/int-class)

Returns the (possibly negative) integer represented by the byte at the
specified `byteOffset` in this object, in two\'s complement binary
representation.

[getUint16](bytedata/getuint16)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

Returns the positive integer represented by the two bytes starting at
the specified `byteOffset` in this object, in unsigned binary form.

[getUint32](bytedata/getuint32)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

Returns the positive integer represented by the four bytes starting at
the specified `byteOffset` in this object, in unsigned binary form.

[getUint64](bytedata/getuint64)([int](../dart-core/int-class)
byteOffset, \[[Endian](endian-class) endian = Endian.big\]) →
[int](../dart-core/int-class)

Returns the positive integer represented by the eight bytes starting at
the specified `byteOffset` in this object, in unsigned binary form.

[getUint8](bytedata/getuint8)([int](../dart-core/int-class) byteOffset)
→ [int](../dart-core/int-class)

Returns the positive integer represented by the byte at the specified
`byteOffset` in this object, in unsigned binary form.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setFloat32](bytedata/setfloat32)([int](../dart-core/int-class)
byteOffset, [double](../dart-core/double-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

Sets the four bytes starting at the specified `byteOffset` in this
object to the IEEE 754 single-precision binary floating-point (binary32)
representation of the specified `value`.

[setFloat64](bytedata/setfloat64)([int](../dart-core/int-class)
byteOffset, [double](../dart-core/double-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

Sets the eight bytes starting at the specified `byteOffset` in this
object to the IEEE 754 double-precision binary floating-point (binary64)
representation of the specified `value`.

[setInt16](bytedata/setint16)([int](../dart-core/int-class) byteOffset,
[int](../dart-core/int-class) value, \[[Endian](endian-class) endian =
Endian.big\]) → void

Sets the two bytes starting at the specified `byteOffset` in this object
to the two\'s complement binary representation of the specified `value`,
which must fit in two bytes.

[setInt32](bytedata/setint32)([int](../dart-core/int-class) byteOffset,
[int](../dart-core/int-class) value, \[[Endian](endian-class) endian =
Endian.big\]) → void

Sets the four bytes starting at the specified `byteOffset` in this
object to the two\'s complement binary representation of the specified
`value`, which must fit in four bytes.

[setInt64](bytedata/setint64)([int](../dart-core/int-class) byteOffset,
[int](../dart-core/int-class) value, \[[Endian](endian-class) endian =
Endian.big\]) → void

Sets the eight bytes starting at the specified `byteOffset` in this
object to the two\'s complement binary representation of the specified
`value`, which must fit in eight bytes.

[setInt8](bytedata/setint8)([int](../dart-core/int-class) byteOffset,
[int](../dart-core/int-class) value) → void

Sets the byte at the specified `byteOffset` in this object to the two\'s
complement binary representation of the specified `value`, which must
fit in a single byte.

[setUint16](bytedata/setuint16)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

Sets the two bytes starting at the specified `byteOffset` in this object
to the unsigned binary representation of the specified `value`, which
must fit in two bytes.

[setUint32](bytedata/setuint32)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

Sets the four bytes starting at the specified `byteOffset` in this
object to the unsigned binary representation of the specified `value`,
which must fit in four bytes.

[setUint64](bytedata/setuint64)([int](../dart-core/int-class)
byteOffset, [int](../dart-core/int-class) value,
\[[Endian](endian-class) endian = Endian.big\]) → void

Sets the eight bytes starting at the specified `byteOffset` in this
object to the unsigned binary representation of the specified `value`,
which must fit in eight bytes.

[setUint8](bytedata/setuint8)([int](../dart-core/int-class) byteOffset,
[int](../dart-core/int-class) value) → void

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
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteData-class.html>
:::
