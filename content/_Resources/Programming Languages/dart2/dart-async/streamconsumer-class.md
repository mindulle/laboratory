[dart:async](../dart-async/dart-async-library){._links-link}

StreamConsumer\<S\> class
=========================

Abstract interface for a \"sink\" accepting multiple entire streams.

A consumer can accept a number of consecutive streams using
[addStream](streamconsumer/addstream), and when no further data need to
be added, the [close](streamconsumer/close) method tells the consumer to
complete its work and shut down.

The [Stream.pipe](stream/pipe) accepts a `StreamConsumer` and will pass
the stream to the consumer\'s [addStream](streamconsumer/addstream)
method. When that completes, it will call [close](streamconsumer/close)
and then complete its own returned future.

Implementers

:   -   [StreamSink](streamsink-class)

Constructors
------------

[StreamConsumer](streamconsumer/streamconsumer)()

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

[addStream](streamconsumer/addstream)([Stream](stream-class)\<S\>
stream) → [Future](future-class)

Consumes the elements of `stream`.

[close](streamconsumer/close)() → [Future](future-class)

Tells the consumer that no further streams will be added.

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
<https://api.dart.dev/stable/2.18.5/dart-async/StreamConsumer-class.html>
:::
