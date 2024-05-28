[dart:async](../dart-async/dart-async-library){._links-link}

RegisterUnaryCallbackHandler typedef
====================================

::: {.section .multi-line-signature}
RegisterUnaryCallbackHandler =
[ZoneUnaryCallback](zoneunarycallback)\<R, T\> Function\<R,
T\>([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class) parent,
[Zone](zone-class) zone, R f(T arg))
:::

The type of a custom
[Zone.registerUnaryCallback](zone/registerunarycallback) implementation
function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The function `f` is the function which was passed to the which was
passed to the [Zone.registerUnaryCallback](zone/registerunarycallback)
of `zone`.

The handler should return either the function `f` or another function
replacing `f`, typically by wrapping `f` in a function which does
something extra before and after invoking `f`

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef RegisterUnaryCallbackHandler = ZoneUnaryCallback<R, T> Function<R, T>(
    Zone self, ZoneDelegate parent, Zone zone, R Function(T arg) f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/RegisterUnaryCallbackHandler.html>
:::
