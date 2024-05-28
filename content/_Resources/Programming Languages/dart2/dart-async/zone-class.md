[dart:async](../dart-async/dart-async-library){._links-link}

Zone class
==========

A zone represents an environment that remains stable across asynchronous
calls.

Code is always executed in the context of a zone, available as
[Zone.current](zone/current). The initial `main` function runs in the
context of the default zone ([Zone.root](zone/root-constant)). Code can
be run in a different zone using either [runZoned](runzoned), to create
a new zone, or [Zone.run](zone/run) to run code in the context of an
existing zone which was created earlier using [Zone.fork](zone/fork).

Developers can create a new zone that overrides some of the
functionality of an existing zone. For example, custom zones can replace
or modify the behavior of `print`, timers, microtasks or how uncaught
errors are handled.

The [Zone](zone-class) class is not subclassable, but users can provide
custom zones by forking an existing zone (usually
[Zone.current](zone/current)) with a
[ZoneSpecification](zonespecification-class). This is similar to
creating a new class that extends the base `Zone` class and that
overrides some methods, except without actually creating a new class.
Instead the overriding methods are provided as functions that explicitly
take the equivalent of their own class, the \"super\" class and the
`this` object as parameters.

Asynchronous callbacks always run in the context of the zone where they
were scheduled. This is implemented using two steps:

1.  the callback is first registered using one of
    [registerCallback](zone/registercallback),
    [registerUnaryCallback](zone/registerunarycallback), or
    [registerBinaryCallback](zone/registerbinarycallback). This allows
    the zone to record that a callback exists and potentially modify it
    (by returning a different callback). The code doing the registration
    (e.g., `Future.then`) also remembers the current zone so that it can
    later run the callback in that zone.
2.  At a later point the registered callback is run in the remembered
    zone, using one of [run](zone/run), [runUnary](zone/rununary) or
    [runBinary](zone/runbinary).

This is all handled internally by the platform code and most users
don\'t need to worry about it. However, developers of new asynchronous
operations, provided by the underlying system, must follow the protocol
to be zone compatible.

For convenience, zones provide [bindCallback](zone/bindcallback) (and
the corresponding [bindUnaryCallback](zone/bindunarycallback) and
[bindBinaryCallback](zone/bindbinarycallback)) to make it easier to
respect the zone contract: these functions first invoke the
corresponding `register` functions and then wrap the returned function
so that it runs in the current zone when it is later asynchronously
invoked.

Similarly, zones provide [bindCallbackGuarded](zone/bindcallbackguarded)
(and the corresponding
[bindUnaryCallbackGuarded](zone/bindunarycallbackguarded) and
[bindBinaryCallbackGuarded](zone/bindbinarycallbackguarded)), when the
callback should be invoked through [Zone.runGuarded](zone/runguarded).

Properties {#instance-properties}
----------

[errorZone](zone/errorzone) → [Zone](zone-class)

::: {.features}
read-only
:::

The error zone is responsible for dealing with uncaught errors.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[parent](zone/parent) → [Zone](zone-class)?

::: {.features}
read-only
:::

The parent zone of the this zone.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[bindBinaryCallback](zone/bindbinarycallback)\<R, T1, T2\>(R callback(T1
argument1, T2 argument2)) → [ZoneBinaryCallback](zonebinarycallback)\<R,
T1, T2\>

Registers the provided `callback` and returns a function that will
execute in this zone.

[bindBinaryCallbackGuarded](zone/bindbinarycallbackguarded)\<T1,
T2\>(void callback(T1 argument1, T2 argument2)) → void Function(T1, T2)

Registers the provided `callback` and returns a function that will
execute in this zone.

[bindCallback](zone/bindcallback)\<R\>(R callback()) →
[ZoneCallback](zonecallback)\<R\>

Registers the provided `callback` and returns a function that will
execute in this zone.

[bindCallbackGuarded](zone/bindcallbackguarded)(void callback()) → void
Function()

Registers the provided `callback` and returns a function that will
execute in this zone.

[bindUnaryCallback](zone/bindunarycallback)\<R, T\>(R callback(T
argument)) → [ZoneUnaryCallback](zoneunarycallback)\<R, T\>

Registers the provided `callback` and returns a function that will
execute in this zone.

[bindUnaryCallbackGuarded](zone/bindunarycallbackguarded)\<T\>(void
callback(T argument)) → void Function(T)

Registers the provided `callback` and returns a function that will
execute in this zone.

[createPeriodicTimer](zone/createperiodictimer)([Duration](../dart-core/duration-class)
period, void callback([Timer](timer-class) timer)) →
[Timer](timer-class)

Creates a periodic [Timer](timer-class) where the callback is executed
in this zone.

[createTimer](zone/createtimer)([Duration](../dart-core/duration-class)
duration, void callback()) → [Timer](timer-class)

Creates a [Timer](timer-class) where the callback is executed in this
zone.

[errorCallback](zone/errorcallback)([Object](../dart-core/object-class)
error, [StackTrace](../dart-core/stacktrace-class)? stackTrace) →
[AsyncError](asyncerror-class)?

Intercepts errors when added programmatically to a
[Future](future-class) or [Stream](stream-class).

[fork](zone/fork)({[ZoneSpecification](zonespecification-class)?
specification,
[Map](../dart-core/map-class)\<[Object](../dart-core/object-class)?,
[Object](../dart-core/object-class)?\>? zoneValues}) →
[Zone](zone-class)

Creates a new zone as a child zone of this zone.

[handleUncaughtError](zone/handleuncaughterror)([Object](../dart-core/object-class)
error, [StackTrace](../dart-core/stacktrace-class) stackTrace) → void

Handles uncaught asynchronous errors.

[inSameErrorZone](zone/insameerrorzone)([Zone](zone-class) otherZone) →
[bool](../dart-core/bool-class)

Whether this zone and `otherZone` are in the same error zone.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[print](zone/print)([String](../dart-core/string-class) line) → void

Prints the given `line`.

[registerBinaryCallback](zone/registerbinarycallback)\<R, T1, T2\>(R
callback(T1 arg1, T2 arg2)) →
[ZoneBinaryCallback](zonebinarycallback)\<R, T1, T2\>

Registers the given callback in this zone.

[registerCallback](zone/registercallback)\<R\>(R callback()) →
[ZoneCallback](zonecallback)\<R\>

Registers the given callback in this zone.

[registerUnaryCallback](zone/registerunarycallback)\<R, T\>(R callback(T
arg)) → [ZoneUnaryCallback](zoneunarycallback)\<R, T\>

Registers the given callback in this zone.

[run](zone/run)\<R\>(R action()) → R

Executes `action` in this zone.

[runBinary](zone/runbinary)\<R, T1, T2\>(R action(T1 argument1, T2
argument2), T1 argument1, T2 argument2) → R

Executes the given `action` with `argument1` and `argument2` in this
zone.

[runBinaryGuarded](zone/runbinaryguarded)\<T1, T2\>(void action(T1
argument1, T2 argument2), T1 argument1, T2 argument2) → void

Executes the given `action` with `argument1` and `argument2` in this
zone and catches synchronous errors.

[runGuarded](zone/runguarded)(void action()) → void

Executes the given `action` in this zone and catches synchronous errors.

[runUnary](zone/rununary)\<R, T\>(R action(T argument), T argument) → R

Executes the given `action` with `argument` in this zone.

[runUnaryGuarded](zone/rununaryguarded)\<T\>(void action(T argument), T
argument) → void

Executes the given `action` with `argument` in this zone and catches
synchronous errors.

[scheduleMicrotask](zone/schedulemicrotask)(void callback()) → void

Runs `callback` asynchronously in this zone.

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

[operator \[\]](zone/operator_get)([Object](../dart-core/object-class)?
key) → dynamic

Retrieves the zone-value associated with `key`.

Static Properties
-----------------

[current](zone/current) → [Zone](zone-class)

::: {.features}
read-only
:::

The zone that is currently active.

Constants
---------

[root](zone/root-constant) → const [Zone](zone-class)
:   The root zone.
    <div>

    `_rootZone`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone-class.html>
:::
