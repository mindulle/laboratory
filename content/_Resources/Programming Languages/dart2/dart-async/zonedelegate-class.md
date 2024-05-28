[dart:async](../dart-async/dart-async-library){._links-link}

ZoneDelegate class
==================

An adapted view of the parent zone.

This class allows the implementation of a zone method to invoke methods
on the parent zone while retaining knowledge of the originating zone.

Custom zones (created through [Zone.fork](zone/fork) or
[runZoned](runzoned)) can provide implementations of most methods of
zones. This is similar to overriding methods on [Zone](zone-class),
except that this mechanism doesn\'t require subclassing.

A custom zone function (provided through a
[ZoneSpecification](zonespecification-class)) typically records or wraps
its parameters and then delegates the operation to its parent zone using
the provided [ZoneDelegate](zonedelegate-class).

While zones have access to their parent zone (through
[Zone.parent](zone/parent)) it is recommended to call the methods on the
provided parent delegate for two reasons:

1.  the delegate methods take an additional `zone` argument which is the
    zone the action has been initiated in.
2.  delegate calls are more efficient, since the implementation knows
    how to skip zones that would just delegate to their parents.

Constructors
------------

[ZoneDelegate](zonedelegate/zonedelegate)()

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

[createPeriodicTimer](zonedelegate/createperiodictimer)([Zone](zone-class)
zone, [Duration](../dart-core/duration-class) period, void
f([Timer](timer-class) timer)) → [Timer](timer-class)

[createTimer](zonedelegate/createtimer)([Zone](zone-class) zone,
[Duration](../dart-core/duration-class) duration, void f()) →
[Timer](timer-class)

[errorCallback](zonedelegate/errorcallback)([Zone](zone-class) zone,
[Object](../dart-core/object-class) error,
[StackTrace](../dart-core/stacktrace-class)? stackTrace) →
[AsyncError](asyncerror-class)?

[fork](zonedelegate/fork)([Zone](zone-class) zone,
[ZoneSpecification](zonespecification-class)? specification,
[Map](../dart-core/map-class)? zoneValues) → [Zone](zone-class)

[handleUncaughtError](zonedelegate/handleuncaughterror)([Zone](zone-class)
zone, [Object](../dart-core/object-class) error,
[StackTrace](../dart-core/stacktrace-class) stackTrace) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[print](zonedelegate/print)([Zone](zone-class) zone,
[String](../dart-core/string-class) line) → void

[registerBinaryCallback](zonedelegate/registerbinarycallback)\<R, T1,
T2\>([Zone](zone-class) zone, R f(T1 arg1, T2 arg2)) →
[ZoneBinaryCallback](zonebinarycallback)\<R, T1, T2\>

[registerCallback](zonedelegate/registercallback)\<R\>([Zone](zone-class)
zone, R f()) → [ZoneCallback](zonecallback)\<R\>

[registerUnaryCallback](zonedelegate/registerunarycallback)\<R,
T\>([Zone](zone-class) zone, R f(T arg)) →
[ZoneUnaryCallback](zoneunarycallback)\<R, T\>

[run](zonedelegate/run)\<R\>([Zone](zone-class) zone, R f()) → R

[runBinary](zonedelegate/runbinary)\<R, T1, T2\>([Zone](zone-class)
zone, R f(T1 arg1, T2 arg2), T1 arg1, T2 arg2) → R

[runUnary](zonedelegate/rununary)\<R, T\>([Zone](zone-class) zone, R f(T
arg), T arg) → R

[scheduleMicrotask](zonedelegate/schedulemicrotask)([Zone](zone-class)
zone, void f()) → void

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
<https://api.dart.dev/stable/2.18.5/dart-async/ZoneDelegate-class.html>
:::
