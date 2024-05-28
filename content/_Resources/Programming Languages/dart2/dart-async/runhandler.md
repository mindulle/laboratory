[dart:async](../dart-async/dart-async-library){._links-link}

RunHandler typedef
==================

::: {.section .multi-line-signature}
RunHandler = R Function\<R\>([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone, R
f())
:::

The type of a custom [Zone.run](zone/run) implementation function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The function `f` is the function which was passed to the
[Zone.run](zone/run) of `zone`.

The default behavior of [Zone.run](zone/run) is to call `f` in the
current zone, `zone`. A custom handler can do things before, after or
instead of calling `f`.

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef RunHandler = R Function<R>(
    Zone self, ZoneDelegate parent, Zone zone, R Function() f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/RunHandler.html>
:::
