[dart:async](../dart-async/dart-async-library){._links-link}

StreamIterator\<T\> class
=========================

An [Iterator](../dart-core/iterator-class)-like interface for the values
of a [Stream](stream-class).

This wraps a [Stream](stream-class) and a subscription on the stream. It
listens on the stream, and completes the future returned by
[moveNext](streamiterator/movenext) when the next value becomes
available.

The stream may be paused between calls to
[moveNext](streamiterator/movenext).

The [current](streamiterator/current) value must only be used after a
future returned by [moveNext](streamiterator/movenext) has completed
with `true`, and only until [moveNext](streamiterator/movenext) is
called again.

Constructors
------------

[StreamIterator](streamiterator/streamiterator)([Stream](stream-class)\<T\>
stream)

::: {.constructor-modifier .features}
factory
:::

Create a [StreamIterator](streamiterator-class) on `stream`.

Properties {#instance-properties}
----------

[current](streamiterator/current) → T

::: {.features}
read-only
:::

The current value of the stream.

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

[cancel](streamiterator/cancel)() → [Future](future-class)

Cancels the stream iterator (and the underlying stream subscription)
early.

[moveNext](streamiterator/movenext)() →
[Future](future-class)\<[bool](../dart-core/bool-class)\>

Wait for the next stream value to be available.

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
<https://api.dart.dev/stable/2.18.5/dart-async/StreamIterator-class.html>
:::
