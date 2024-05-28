[dart:async](../dart-async/dart-async-library){._links-link}

runZoned\<R\> function
======================

::: {.section .multi-line-signature}
R runZoned\<R\>(

1.  R body( ),
2.  {[Map](../dart-core/map-class)\<[Object](../dart-core/object-class)?,
    [Object](../dart-core/object-class)?\>? zoneValues,
3.  [ZoneSpecification](zonespecification-class)? zoneSpecification,
4.  @[Deprecated](../dart-core/deprecated-class)(\"Use runZonedGuarded
    instead\") [Function](../dart-core/function-class)? onError}

)
:::

Runs `body` in its own zone.

Creates a new zone using [Zone.fork](zone/fork) based on
`zoneSpecification` and `zoneValues`, then runs `body` in that zone and
returns the result.

If `onError` is provided, it must have one of the types

-   `void Function(Object)`
-   `void Function(Object, StackTrace)` and the `onError` handler is
    used *both* to handle asynchronous errors by overriding
    [ZoneSpecification.handleUncaughtError](zonespecification/handleuncaughterror)
    in `zoneSpecification`, if any, *and* to handle errors thrown
    synchronously by the call to `body`.

If an error occurs synchronously in `body`, then throwing in the
`onError` handler makes the call to `runZone` throw that error, and
otherwise the call to `runZoned` attempt to return `null`.

If the zone specification has a `handleUncaughtError` value or the
`onError` parameter is provided, the zone becomes an error-zone.

Errors will never cross error-zone boundaries by themselves. Errors that
try to cross error-zone boundaries are considered uncaught in their
originating error zone.

``` {.language-dart data-language="dart"}
var future = Future.value(499);
runZoned(() {
  var future2 = future.then((_) { throw "error in first error-zone"; });
  runZoned(() {
    var future3 = future2.catchError((e) { print("Never reached!"); });
  }, onError: (e, s) { print("unused error handler"); });
}, onError: (e, s) { print("catches error of first error-zone."); });
```

Example:

``` {.language-dart data-language="dart"}
runZoned(() {
  Future(() { throw "asynchronous error"; });
}, onError: (e, s) => print(e));  // Will print "asynchronous error".
```

It is possible to manually pass an error from one error zone to another
by re-throwing it in the new zone. If `onError` throws, that error will
occur in the original zone where [runZoned](runzoned) was called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
R runZoned<R>(R body(),
    {Map<Object?, Object?>? zoneValues,
    ZoneSpecification? zoneSpecification,
    @Deprecated("Use runZonedGuarded instead") Function? onError}) {
  checkNotNullable(body, "body");
  if (onError != null) {
    // TODO: Remove this when code have been migrated off using [onError].
    if (onError is! void Function(Object, StackTrace)) {
      if (onError is void Function(Object)) {
        var originalOnError = onError;
        onError = (Object error, StackTrace stack) => originalOnError(error);
      } else {
        throw ArgumentError.value(onError, "onError",
            "Must be Function(Object) or Function(Object, StackTrace)");
      }
    }
    return runZonedGuarded(body, onError,
        zoneSpecification: zoneSpecification, zoneValues: zoneValues) as R;
  }
  return _runZoned<R>(body, zoneValues, zoneSpecification);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/runZoned.html>
:::
