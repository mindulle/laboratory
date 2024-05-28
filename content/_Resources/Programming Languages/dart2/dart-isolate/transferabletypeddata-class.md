[dart:isolate](../dart-isolate/dart-isolate-library){._links-link}

TransferableTypedData class
===========================

An efficiently transferable sequence of byte values.

A [TransferableTypedData](transferabletypeddata-class) is created from a
number of bytes. This will take time proportional to the number of
bytes.

The [TransferableTypedData](transferabletypeddata-class) can be moved
between isolates, so sending it through a send port will only take
constant time.

When sent this way, the local transferable can no longer be
materialized, and the received object is now the only way to materialize
the data.

Annotations

:   -   \@Since(\"2.3.2\")

Constructors
------------

[TransferableTypedData.fromList](transferabletypeddata/transferabletypeddata.fromlist)([List](../dart-core/list-class)\<[TypedData](../dart-typed_data/typeddata-class)\>
list)

::: {.constructor-modifier .features}
factory
:::

Creates a new [TransferableTypedData](transferabletypeddata-class)
containing the bytes of `list`.

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

[materialize](transferabletypeddata/materialize)() →
[ByteBuffer](../dart-typed_data/bytebuffer-class)

Creates a new [ByteBuffer](../dart-typed_data/bytebuffer-class)
containing the bytes stored in this
[TransferableTypedData](transferabletypeddata-class).

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
<https://api.dart.dev/stable/2.18.5/dart-isolate/TransferableTypedData-class.html>
:::
