[dart:async](../dart-async/dart-async-library){._links-link}

CreatePeriodicTimerHandler typedef
==================================

::: {.section .multi-line-signature}
CreatePeriodicTimerHandler = [Timer](timer-class)
Function([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class)
parent, [Zone](zone-class) zone, [Duration](../dart-core/duration-class)
period, void f([Timer](timer-class) timer))
:::

The type of a custom
[Zone.createPeriodicTimer](zone/createperiodictimer) implementation
function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The callback function `f` and `period` are the ones which were passed to
[Zone.createPeriodicTimer](zone/createperiodictimer) of `zone` (possibly
through the [Timer.periodic](timer/timer.periodic) constructor).

The custom handler can choose to replace the function `f` with one that
does something before, after or instead of calling `f`, and then call
`parent.createTimer(zone, replacement)`. or it can implement its own
timer queue, which typically still depends on `parent.createTimer` to as
a way to get started.

The function should return a [Timer](timer-class) object which can be
used to inspect and control the scheduled timer callbacks.

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef Timer CreatePeriodicTimerHandler(Zone self, ZoneDelegate parent,
    Zone zone, Duration period, void f(Timer timer));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/CreatePeriodicTimerHandler.html>
:::
