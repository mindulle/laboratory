[dart:async](../dart-async/dart-async-library){._links-link}

ScheduleMicrotaskHandler typedef
================================

::: {.section .multi-line-signature}
ScheduleMicrotaskHandler = void Function([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone, void
f())
:::

The type of a custom [Zone.scheduleMicrotask](zone/schedulemicrotask)
implementation function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The function `f` is the function which was passed to
[Zone.scheduleMicrotask](zone/schedulemicrotask) of `zone`.

The custom handler can choose to replace the function `f` with one that
does something before, after or instead of calling `f`, and then call
`parent.scheduleMicrotask(zone, replacement)`. or it can implement its
own microtask scheduling queue, which typically still depends on
`parent.scheduleMicrotask` to as a way to get started.

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef void ScheduleMicrotaskHandler(
    Zone self, ZoneDelegate parent, Zone zone, void f());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/ScheduleMicrotaskHandler.html>
:::
