[dart:async](../dart-async/dart-async-library){._links-link}

RunBinaryHandler typedef
========================

::: {.section .multi-line-signature}
RunBinaryHandler = R Function\<R, T1, T2\>([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone, R
f(T1 arg1, T2 arg2), T1 arg1, T2 arg2)
:::

The type of a custom [Zone.runBinary](zone/runbinary) implementation
function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The function `f` and values `arg1` and `arg2` are the function and
arguments which was passed to the [Zone.runBinary](zone/runbinary) of
`zone`.

The default behavior of [Zone.runUnary](zone/rununary) is to call `f`
with arguments `arg1` and `arg2` in the current zone, `zone`. A custom
handler can do things before, after or instead of calling `f`.

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef RunBinaryHandler = R Function<R, T1, T2>(Zone self, ZoneDelegate parent,
    Zone zone, R Function(T1 arg1, T2 arg2) f, T1 arg1, T2 arg2);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/RunBinaryHandler.html>
:::
