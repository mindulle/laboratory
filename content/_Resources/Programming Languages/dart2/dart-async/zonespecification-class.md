[dart:async](../dart-async/dart-async-library){._links-link}

ZoneSpecification class
=======================

A parameter object with custom zone function handlers for
[Zone.fork](zone/fork).

A zone specification is a parameter object passed to
[Zone.fork](zone/fork) and any underlying [ForkHandler](forkhandler)
custom implementations. The individual handlers, if set to a non-null
value, will be the implementation of the corresponding
[Zone](zone-class) methods for a forked zone created using this zone
specification.

Handlers have the same signature as the same-named methods on
[Zone](zone-class), but receive three additional arguments:

1.  The zone the handlers are attached to (the \"self\" zone). This is
    the zone created by [Zone.fork](zone/fork) where the handler is
    passed as part of the zone delegation.
2.  A [ZoneDelegate](zonedelegate-class) to the parent zone.
3.  The \"current\" zone at the time the request was made. The self zone
    is always a parent zone of the current zone.

Handlers can either stop propagating the request (by simply not calling
the parent handler), or forward to the parent zone, potentially
modifying the arguments on the way.

Constructors
------------

[ZoneSpecification](zonespecification/zonespecification)({[HandleUncaughtErrorHandler](handleuncaughterrorhandler)?
handleUncaughtError, [RunHandler](runhandler)? run,
[RunUnaryHandler](rununaryhandler)? runUnary,
[RunBinaryHandler](runbinaryhandler)? runBinary,
[RegisterCallbackHandler](registercallbackhandler)? registerCallback,
[RegisterUnaryCallbackHandler](registerunarycallbackhandler)?
registerUnaryCallback,
[RegisterBinaryCallbackHandler](registerbinarycallbackhandler)?
registerBinaryCallback, [ErrorCallbackHandler](errorcallbackhandler)?
errorCallback, [ScheduleMicrotaskHandler](schedulemicrotaskhandler)?
scheduleMicrotask, [CreateTimerHandler](createtimerhandler)?
createTimer, [CreatePeriodicTimerHandler](createperiodictimerhandler)?
createPeriodicTimer, [PrintHandler](printhandler)? print,
[ForkHandler](forkhandler)? fork})

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Creates a specification with the provided handlers.

[ZoneSpecification.from](zonespecification/zonespecification.from)([ZoneSpecification](zonespecification-class)
other, {[HandleUncaughtErrorHandler](handleuncaughterrorhandler)?
handleUncaughtError, [RunHandler](runhandler)? run,
[RunUnaryHandler](rununaryhandler)? runUnary,
[RunBinaryHandler](runbinaryhandler)? runBinary,
[RegisterCallbackHandler](registercallbackhandler)? registerCallback,
[RegisterUnaryCallbackHandler](registerunarycallbackhandler)?
registerUnaryCallback,
[RegisterBinaryCallbackHandler](registerbinarycallbackhandler)?
registerBinaryCallback, [ErrorCallbackHandler](errorcallbackhandler)?
errorCallback, [ScheduleMicrotaskHandler](schedulemicrotaskhandler)?
scheduleMicrotask, [CreateTimerHandler](createtimerhandler)?
createTimer, [CreatePeriodicTimerHandler](createperiodictimerhandler)?
createPeriodicTimer, [PrintHandler](printhandler)? print,
[ForkHandler](forkhandler)? fork})

::: {.constructor-modifier .features}
factory
:::

Creates a specification from `other` and provided handlers.

Properties {#instance-properties}
----------

[createPeriodicTimer](zonespecification/createperiodictimer) →
[CreatePeriodicTimerHandler](createperiodictimerhandler)?

::: {.features}
read-only
:::

A custom [Zone.createPeriodicTimer](zone/createperiodictimer)
implementation for a new zone.

[createTimer](zonespecification/createtimer) →
[CreateTimerHandler](createtimerhandler)?

::: {.features}
read-only
:::

A custom [Zone.createTimer](zone/createtimer) implementation for a new
zone.

[errorCallback](zonespecification/errorcallback) →
[ErrorCallbackHandler](errorcallbackhandler)?

::: {.features}
read-only
:::

A custom [Zone.errorCallback](zone/errorcallback) implementation for a
new zone.

[fork](zonespecification/fork) → [ForkHandler](forkhandler)?

::: {.features}
read-only
:::

A custom [Zone.handleUncaughtError](zone/handleuncaughterror)
implementation for a new zone.

[handleUncaughtError](zonespecification/handleuncaughterror) →
[HandleUncaughtErrorHandler](handleuncaughterrorhandler)?

::: {.features}
read-only
:::

A custom [Zone.handleUncaughtError](zone/handleuncaughterror)
implementation for a new zone.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[print](zonespecification/print) → [PrintHandler](printhandler)?

::: {.features}
read-only
:::

A custom [Zone.print](zone/print) implementation for a new zone.

[registerBinaryCallback](zonespecification/registerbinarycallback) →
[RegisterBinaryCallbackHandler](registerbinarycallbackhandler)?

::: {.features}
read-only
:::

A custom [Zone.registerBinaryCallback](zone/registerbinarycallback)
implementation for a new zone.

[registerCallback](zonespecification/registercallback) →
[RegisterCallbackHandler](registercallbackhandler)?

::: {.features}
read-only
:::

A custom [Zone.registerCallback](zone/registercallback) implementation
for a new zone.

[registerUnaryCallback](zonespecification/registerunarycallback) →
[RegisterUnaryCallbackHandler](registerunarycallbackhandler)?

::: {.features}
read-only
:::

A custom [Zone.registerUnaryCallback](zone/registerunarycallback)
implementation for a new zone.

[run](zonespecification/run) → [RunHandler](runhandler)?

::: {.features}
read-only
:::

A custom [Zone.run](zone/run) implementation for a new zone.

[runBinary](zonespecification/runbinary) →
[RunBinaryHandler](runbinaryhandler)?

::: {.features}
read-only
:::

A custom [Zone.runBinary](zone/runbinary) implementation for a new zone.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[runUnary](zonespecification/rununary) →
[RunUnaryHandler](rununaryhandler)?

::: {.features}
read-only
:::

A custom [Zone.runUnary](zone/rununary) implementation for a new zone.

[scheduleMicrotask](zonespecification/schedulemicrotask) →
[ScheduleMicrotaskHandler](schedulemicrotaskhandler)?

::: {.features}
read-only
:::

A custom [Zone.scheduleMicrotask](zone/schedulemicrotask) implementation
for a new zone.

Methods {#instance-methods}
-------

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
<https://api.dart.dev/stable/2.18.5/dart-async/ZoneSpecification-class.html>
:::
