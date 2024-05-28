[dart:async](../dart-async/dart-async-library){._links-link}

HandleUncaughtErrorHandler typedef
==================================

::: {.section .multi-line-signature}
HandleUncaughtErrorHandler = void Function([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone,
[Object](../dart-core/object-class) error,
[StackTrace](../dart-core/stacktrace-class) stackTrace)
:::

The type of a custom
[Zone.handleUncaughtError](zone/handleuncaughterror) implementation
function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The `error` and `stackTrace` are the error and stack trace that was
uncaught in `zone`.

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

If the uncaught error handler throws, the error will be passed to
`parent.handleUncaughtError`. If the thrown object is `error`, the throw
is considered a re-throw and the original `stackTrace` is retained. This
allows an asynchronous error to leave the error zone.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef HandleUncaughtErrorHandler = void Function(Zone self,
    ZoneDelegate parent, Zone zone, Object error, StackTrace stackTrace);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/HandleUncaughtErrorHandler.html>
:::
