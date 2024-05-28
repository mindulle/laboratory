[dart:async](../dart-async/dart-async-library){._links-link}

ErrorCallbackHandler typedef
============================

::: {.section .multi-line-signature}
ErrorCallbackHandler = [AsyncError](asyncerror-class)?
Function([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class)
parent, [Zone](zone-class) zone, [Object](../dart-core/object-class)
error, [StackTrace](../dart-core/stacktrace-class)? stackTrace)
:::

The type of a custom [Zone.errorCallback](zone/errorcallback)
implementation function.

Receives the [Zone](zone-class) that the handler was registered on as
`self`, a delegate forwarding to the handlers of `self`\'s parent zone
as `parent`, and the current zone where the error was uncaught as
`zone`, which will have `self` as a parent zone.

The `error` and `stackTrace` are the error and stack trace passed to
[Zone.errorCallback](zone/errorcallback) of `zone`.

The function should return either `null` if it doesn\'t want to replace
the original error and stack trace, or an [AsyncError](asyncerror-class)
containing a replacement error and stack trace which will be used to
replace the originals.

The error callback handler must not throw.

The function must only access zone-related functionality through `self`,
`parent` or `zone`. It should not depend on the current zone
([Zone.current](zone/current)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef AsyncError? ErrorCallbackHandler(Zone self, ZoneDelegate parent,
    Zone zone, Object error, StackTrace? stackTrace);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/ErrorCallbackHandler.html>
:::
