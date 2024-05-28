[dart:async](../../dart-async/dart-async-library){._links-link}

ZoneSpecification constructor
=============================

::: {.section .multi-line-signature}
const ZoneSpecification(

1.  {[HandleUncaughtErrorHandler](../handleuncaughterrorhandler)?
    handleUncaughtError,
2.  [RunHandler](../runhandler)? run,
3.  [RunUnaryHandler](../rununaryhandler)? runUnary,
4.  [RunBinaryHandler](../runbinaryhandler)? runBinary,
5.  [RegisterCallbackHandler](../registercallbackhandler)?
    registerCallback,
6.  [RegisterUnaryCallbackHandler](../registerunarycallbackhandler)?
    registerUnaryCallback,
7.  [RegisterBinaryCallbackHandler](../registerbinarycallbackhandler)?
    registerBinaryCallback,
8.  [ErrorCallbackHandler](../errorcallbackhandler)? errorCallback,
9.  [ScheduleMicrotaskHandler](../schedulemicrotaskhandler)?
    scheduleMicrotask,
10. [CreateTimerHandler](../createtimerhandler)? createTimer,
11. [CreatePeriodicTimerHandler](../createperiodictimerhandler)?
    createPeriodicTimer,
12. [PrintHandler](../printhandler)? print,
13. [ForkHandler](../forkhandler)? fork}

)
:::

Creates a specification with the provided handlers.

If the `handleUncaughtError` is provided, the new zone will be a new
\"error zone\" which will prevent errors from flowing into other error
zones (see [Zone.errorZone](../zone/errorzone),
[Zone.inSameErrorZone](../zone/insameerrorzone)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const factory ZoneSpecification(
    {HandleUncaughtErrorHandler? handleUncaughtError,
    RunHandler? run,
    RunUnaryHandler? runUnary,
    RunBinaryHandler? runBinary,
    RegisterCallbackHandler? registerCallback,
    RegisterUnaryCallbackHandler? registerUnaryCallback,
    RegisterBinaryCallbackHandler? registerBinaryCallback,
    ErrorCallbackHandler? errorCallback,
    ScheduleMicrotaskHandler? scheduleMicrotask,
    CreateTimerHandler? createTimer,
    CreatePeriodicTimerHandler? createPeriodicTimer,
    PrintHandler? print,
    ForkHandler? fork}) = _ZoneSpecification;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/ZoneSpecification/ZoneSpecification.html>
:::
