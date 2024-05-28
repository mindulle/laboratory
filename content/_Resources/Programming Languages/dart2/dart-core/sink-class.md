[dart:core](../dart-core/dart-core-library){._links-link}

Sink\<T\> class
===============

A generic destination for data.

Multiple data values can be put into a sink, and when no more data is
available, the sink should be closed.

This is a generic interface that other data receivers can implement.

Implementers

:   -   [ChunkedConversionSink](../dart-convert/chunkedconversionsink-class)
    -   [EventSink](../dart-async/eventsink-class)

Constructors
------------

[Sink](sink/sink)()

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[add](sink/add)(T data) → void

Adds `data` to the sink.

[close](sink/close)() → void

Closes the sink.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Sink-class.html>
:::
