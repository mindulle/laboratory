[dart:async](../../dart-async/dart-async-library){._links-link}

ZoneSpecification.from constructor
==================================

::: {.section .multi-line-signature}
ZoneSpecification.from(

1.  [ZoneSpecification](../zonespecification-class) other,
2.  {[HandleUncaughtErrorHandler](../handleuncaughterrorhandler)?
    handleUncaughtError,
3.  [RunHandler](../runhandler)? run,
4.  [RunUnaryHandler](../rununaryhandler)? runUnary,
5.  [RunBinaryHandler](../runbinaryhandler)? runBinary,
6.  [RegisterCallbackHandler](../registercallbackhandler)?
    registerCallback,
7.  [RegisterUnaryCallbackHandler](../registerunarycallbackhandler)?
    registerUnaryCallback,
8.  [RegisterBinaryCallbackHandler](../registerbinarycallbackhandler)?
    registerBinaryCallback,
9.  [ErrorCallbackHandler](../errorcallbackhandler)? errorCallback,
10. [ScheduleMicrotaskHandler](../schedulemicrotaskhandler)?
    scheduleMicrotask,
11. [CreateTimerHandler](../createtimerhandler)? createTimer,
12. [CreatePeriodicTimerHandler](../createperiodictimerhandler)?
    createPeriodicTimer,
13. [PrintHandler](../printhandler)? print,
14. [ForkHandler](../forkhandler)? fork}

)
:::

Creates a specification from `other` and provided handlers.

The created zone specification has the handlers of `other` and any
individually provided handlers. If a handler is provided both through
`other` and individually, the individually provided handler overrides
the one from `other`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ZoneSpecification.from(ZoneSpecification other,
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
    ForkHandler? fork}) {
  return new ZoneSpecification(
      handleUncaughtError: handleUncaughtError ?? other.handleUncaughtError,
      run: run ?? other.run,
      runUnary: runUnary ?? other.runUnary,
      runBinary: runBinary ?? other.runBinary,
      registerCallback: registerCallback ?? other.registerCallback,
      registerUnaryCallback:
          registerUnaryCallback ?? other.registerUnaryCallback,
      registerBinaryCallback:
          registerBinaryCallback ?? other.registerBinaryCallback,
      errorCallback: errorCallback ?? other.errorCallback,
      scheduleMicrotask: scheduleMicrotask ?? other.scheduleMicrotask,
      createTimer: createTimer ?? other.createTimer,
      createPeriodicTimer: createPeriodicTimer ?? other.createPeriodicTimer,
      print: print ?? other.print,
      fork: fork ?? other.fork);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/ZoneSpecification/ZoneSpecification.from.html>
:::
