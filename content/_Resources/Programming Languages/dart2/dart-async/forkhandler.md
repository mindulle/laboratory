[dart:async](../dart-async/dart-async-library){._links-link}

ForkHandler typedef
===================

::: {.section .multi-line-signature}
ForkHandler = [Zone](zone-class) Function([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone,
[ZoneSpecification](zonespecification-class)? specification,
[Map](../dart-core/map-class)\<[Object](../dart-core/object-class)?,
[Object](../dart-core/object-class)?\>? zoneValues)
:::

The type of a custom [Zone.fork](zone/fork) implementation function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The handler should create a new zone with `zone` as its immediate parent
zone.

The `specification` and `zoneValues` are the ones which were passed to
[Zone.fork](zone/fork) of `zone`. They specify the custom zone handlers
and zone variables that the new zone should have.

The custom handler can change the specification or zone values before
calling `parent.fork(zone, specification, zoneValues)`, but it has to
call the `parent`\'s [ZoneDelegate.fork](zonedelegate/fork) in order to
create a valid [Zone](zone-class) object.

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef Zone ForkHandler(Zone self, ZoneDelegate parent, Zone zone,
    ZoneSpecification? specification, Map<Object?, Object?>? zoneValues);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/ForkHandler.html>
:::
