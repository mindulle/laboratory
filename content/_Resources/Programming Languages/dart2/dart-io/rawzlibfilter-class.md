[dart:io](../dart-io/dart-io-library){._links-link}

RawZLibFilter class
===================

The [RawZLibFilter](rawzlibfilter-class) class provides a low-level
interface to zlib.

Constructors
------------

[RawZLibFilter.deflateFilter](rawzlibfilter/rawzlibfilter.deflatefilter)({[bool](../dart-core/bool-class)
gzip = false, [int](../dart-core/int-class) level =
ZLibOption.defaultLevel, [int](../dart-core/int-class) windowBits =
ZLibOption.defaultWindowBits, [int](../dart-core/int-class) memLevel =
ZLibOption.defaultMemLevel, [int](../dart-core/int-class) strategy =
ZLibOption.strategyDefault,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?
dictionary, [bool](../dart-core/bool-class) raw = false})

::: {.constructor-modifier .features}
factory
:::

Returns a a [RawZLibFilter](rawzlibfilter-class) whose
[process](rawzlibfilter/process) and
[processed](rawzlibfilter/processed) methods compress data.

[RawZLibFilter.inflateFilter](rawzlibfilter/rawzlibfilter.inflatefilter)({[int](../dart-core/int-class)
windowBits = ZLibOption.defaultWindowBits,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?
dictionary, [bool](../dart-core/bool-class) raw = false})

::: {.constructor-modifier .features}
factory
:::

Returns a a [RawZLibFilter](rawzlibfilter-class) whose
[process](rawzlibfilter/process) and
[processed](rawzlibfilter/processed) methods decompress data.

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

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[process](rawzlibfilter/process)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
data, [int](../dart-core/int-class) start, [int](../dart-core/int-class)
end) → void

Process a chunk of data.

[processed](rawzlibfilter/processed)({[bool](../dart-core/bool-class)
flush = true, [bool](../dart-core/bool-class) end = false}) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?

Get a chunk of processed data.

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
<https://api.dart.dev/stable/2.18.5/dart-io/RawZLibFilter-class.html>
:::
