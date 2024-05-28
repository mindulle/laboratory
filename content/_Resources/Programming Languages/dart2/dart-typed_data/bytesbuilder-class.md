[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

BytesBuilder class
==================

Builds a list of bytes, allowing bytes and lists of bytes to be added at
the end.

Used to efficiently collect bytes and lists of bytes.

Constructors
------------

[BytesBuilder](bytesbuilder/bytesbuilder)({[bool](../dart-core/bool-class)
copy = true})

::: {.constructor-modifier .features}
factory
:::

Construct a new empty [BytesBuilder](bytesbuilder-class).

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](bytesbuilder/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the buffer is empty.

[isNotEmpty](bytesbuilder/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the buffer is non-empty.

[length](bytesbuilder/length) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The number of bytes in this builder.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[add](bytesbuilder/add)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
bytes) → void

Appends `bytes` to the current contents of this builder.

[addByte](bytesbuilder/addbyte)([int](../dart-core/int-class) byte) →
void

Appends `byte` to the current contents of this builder.

[clear](bytesbuilder/clear)() → void

Clears the contents of this builder.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[takeBytes](bytesbuilder/takebytes)() → [Uint8List](uint8list-class)

Returns the bytes currently contained in this builder and clears it.

[toBytes](bytesbuilder/tobytes)() → [Uint8List](uint8list-class)

Returns a copy of the current byte contents of this builder.

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
<https://api.dart.dev/stable/2.18.5/dart-typed_data/BytesBuilder-class.html>
:::
