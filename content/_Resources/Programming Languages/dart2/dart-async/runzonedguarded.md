[dart:async](../dart-async/dart-async-library){._links-link}

runZonedGuarded\<R\> function
=============================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.8\")

</div>

R? runZonedGuarded\<R\>(

1.  R body( ),
2.  void onError(
    1.  [Object](../dart-core/object-class) error,
    2.  [StackTrace](../dart-core/stacktrace-class) stack

    ),
3.  {[Map](../dart-core/map-class)\<[Object](../dart-core/object-class)?,
    [Object](../dart-core/object-class)?\>? zoneValues,
4.  [ZoneSpecification](zonespecification-class)? zoneSpecification}

)
:::

Runs `body` in its own error zone.

Creates a new zone using [Zone.fork](zone/fork) based on
`zoneSpecification` and `zoneValues`, then runs `body` in that zone and
returns the result.

The `onError` function is used *both* to handle asynchronous errors by
overriding
[ZoneSpecification.handleUncaughtError](zonespecification/handleuncaughterror)
in `zoneSpecification`, if any, *and* to handle errors thrown
synchronously by the call to `body`.

If an error occurs synchronously in `body`, then throwing in the
`onError` handler makes the call to `runZonedGuarded` throw that error,
and otherwise the call to `runZonedGuarded` returns `null`.

The zone will always be an error-zone.

Errors will never cross error-zone boundaries by themselves. Errors that
try to cross error-zone boundaries are considered uncaught in their
originating error zone.

``` {.language-dart data-language="dart"}
var future = Future.value(499);
runZonedGuarded(() {
  var future2 = future.then((_) { throw "error in first error-zone"; });
  runZonedGuarded(() {
    var future3 = future2.catchError((e) { print("Never reached!"); });
  }, (e, s) { print("unused error handler"); });
}, (e, s) { print("catches error of first error-zone."); });
```

Example:

``` {.language-dart data-language="dart"}
runZonedGuarded(() {
  Future(() { throw "asynchronous error"; });
}, (e, s) => print(e));  // Will print "asynchronous error".
```

It is possible to manually pass an error from one error zone to another
by re-throwing it in the new zone. If `onError` throws, that error will
occur in the original zone where [runZoned](runzoned) was called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.8")
R? runZonedGuarded<R>(R body(), void onError(Object error, StackTrace stack),
    {Map<Object?, Object?>? zoneValues, ZoneSpecification? zoneSpecification}) {
  checkNotNullable(body, "body");
  checkNotNullable(onError, "onError");
  _Zone parentZone = Zone._current;
  HandleUncaughtErrorHandler errorHandler = (Zone self, ZoneDelegate parent,
      Zone zone, Object error, StackTrace stackTrace) {
    try {
      parentZone.runBinary(onError, error, stackTrace);
    } catch (e, s) {
      if (identical(e, error)) {
        parent.handleUncaughtError(zone, error, stackTrace);
      } else {
        parent.handleUncaughtError(zone, e, s);
      }
    }
  };
  if (zoneSpecification == null) {
    zoneSpecification =
        new ZoneSpecification(handleUncaughtError: errorHandler);
  } else {
    zoneSpecification = ZoneSpecification.from(zoneSpecification,
        handleUncaughtError: errorHandler);
  }
  try {
    return _runZoned<R>(body, zoneValues, zoneSpecification);
  } catch (error, stackTrace) {
    onError(error, stackTrace);
  }
  return null;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/runZonedGuarded.html>
:::
