[dart:io](../dart-io/dart-io-library){._links-link}

ConnectionTask\<S\> class
=========================

A cancelable connection attempt.

Returned by the `startConnect` methods on client-side socket types `S`,
`ConnectionTask<S>` allows cancelling an attempt to connect to a host.

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

[socket](connectiontask/socket) →
[Future](../dart-async/future-class)\<S\>

::: {.features}
final
:::

A `Future` that completes with value that `S.connect()` would return
unless [cancel](connectiontask/cancel) is called on this
[ConnectionTask](connectiontask-class).

Methods {#instance-methods}
-------

[cancel](connectiontask/cancel)() → void

Cancels the connection attempt.

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
<https://api.dart.dev/stable/2.18.5/dart-io/ConnectionTask-class.html>
:::
