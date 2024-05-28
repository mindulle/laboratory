[dart:async](../dart-async/dart-async-library){._links-link}

RegisterBinaryCallbackHandler typedef
=====================================

::: {.section .multi-line-signature}
RegisterBinaryCallbackHandler =
[ZoneBinaryCallback](zonebinarycallback)\<R, T1, T2\> Function\<R, T1,
T2\>([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class) parent,
[Zone](zone-class) zone, R f(T1 arg1, T2 arg2))
:::

The type of a custom
[Zone.registerBinaryCallback](zone/registerbinarycallback)
implementation function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The function `f` is the function which was passed to the which was
passed to the [Zone.registerBinaryCallback](zone/registerbinarycallback)
of `zone`.

The handler should return either the function `f` or another function
replacing `f`, typically by wrapping `f` in a function which does
something extra before and after invoking `f`

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef RegisterBinaryCallbackHandler
    = ZoneBinaryCallback<R, T1, T2> Function<R, T1, T2>(Zone self,
        ZoneDelegate parent, Zone zone, R Function(T1 arg1, T2 arg2) f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/RegisterBinaryCallbackHandler.html>
:::
