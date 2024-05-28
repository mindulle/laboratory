[dart:io](../dart-io/dart-io-library){._links-link}

RawSocketEvent class
====================

Events for the [RawSocket](rawsocket-class).

These event objects are used by the [Stream](../dart-async/stream-class)
behavior of [RawSocket](rawsocket-class) (for example
[RawSocket.listen](../dart-async/stream/listen),
[RawSocket.forEach](../dart-async/stream/foreach)) when the socket\'s
state change.

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

[toString](rawsocketevent/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
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

Constants
---------

[closed](rawsocketevent/closed-constant) → const [RawSocketEvent](rawsocketevent-class)
:   An event indicates the socket is closed.
    <div>

    `const RawSocketEvent._(3)`

    </div>

[read](rawsocketevent/read-constant) → const [RawSocketEvent](rawsocketevent-class)
:   An event indicates the socket is ready to be read.
    <div>

    `const RawSocketEvent._(0)`

    </div>

[readClosed](rawsocketevent/readclosed-constant) → const [RawSocketEvent](rawsocketevent-class)
:   An event indicates the reading from the socket is closed
    <div>

    `const RawSocketEvent._(2)`

    </div>

[write](rawsocketevent/write-constant) → const [RawSocketEvent](rawsocketevent-class)
:   An event indicates the socket is ready to write.
    <div>

    `const RawSocketEvent._(1)`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketEvent-class.html>
:::
