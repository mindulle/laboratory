[dart:async](../../dart-async/dart-async-library){._links-link}

wait\<T\> method
================

::: {.section .multi-line-signature}
[Future](../future-class)\<[List](../../dart-core/list-class)\<T\>\>
wait\<T\>(

1.  [Iterable](../../dart-core/iterable-class)\<[Future](../future-class)\<T\>\>
    futures,
2.  {[bool](../../dart-core/bool-class) eagerError = false,
3.  void cleanUp(
    1.  T successValue

    )?}

)
:::

Waits for multiple futures to complete and collects their results.

Returns a future which will complete once all the provided futures have
completed, either with their results, or with an error if any of the
provided futures fail.

The value of the returned future will be a list of all the values that
were produced in the order that the futures are provided by iterating
`futures`.

If any future completes with an error, then the returned future
completes with that error. If further futures also complete with errors,
those errors are discarded.

If `eagerError` is true, the returned future completes with an error
immediately on the first error from one of the futures. Otherwise all
futures must complete before the returned future is completed (still
with the first error; the remaining errors are silently dropped).

In the case of an error, `cleanUp` (if provided), is invoked on any
non-null result of successful futures. This makes it possible to
`cleanUp` resources that would otherwise be lost (since the returned
future does not provide access to these values). The `cleanUp` function
is unused if there is no error.

The call to `cleanUp` should not throw. If it does, the error will be an
uncaught asynchronous error.

Example:

``` {.language-dart data-language="dart"}
void main() async {
  var value = await Future.wait([delayedNumber(), delayedString()]);
  print(value); // [2, result]
}

Future<int> delayedNumber() async {
  await Future.delayed(const Duration(seconds: 2));
  return 2;
}

Future<String> delayedString() async {
  await Future.delayed(const Duration(seconds: 2));
  return 'result';
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:recognized", "other")
static Future<List<T>> wait<T>(Iterable<Future<T>> futures,
    {bool eagerError = false, void cleanUp(T successValue)?}) {
  // This is a VM recognised method, and the _future variable is deliberately
  // allocated in a specific slot in the closure context for stack unwinding.
  final _Future<List<T>> _future = _Future<List<T>>();
  List<T?>? values; // Collects the values. Set to null on error.
  int remaining = 0; // How many futures are we waiting for.
  late Object error; // The first error from a future.
  late StackTrace stackTrace; // The stackTrace that came with the error.

  // Handle an error from any of the futures.
  void handleError(Object theError, StackTrace theStackTrace) {
    remaining--;
    List<T?>? valueList = values;
    if (valueList != null) {
      if (cleanUp != null) {
        for (var value in valueList) {
          if (value != null) {
            // Ensure errors from cleanUp are uncaught.
            T cleanUpValue = value;
            new Future.sync(() {
              cleanUp(cleanUpValue);
            });
          }
        }
      }
      values = null;
      if (remaining == 0 || eagerError) {
        _future._completeError(theError, theStackTrace);
      } else {
        error = theError;
        stackTrace = theStackTrace;
      }
    } else if (remaining == 0 && !eagerError) {
      _future._completeError(error, stackTrace);
    }
  }

  try {
    // As each future completes, put its value into the corresponding
    // position in the list of values.
    for (var future in futures) {
      int pos = remaining;
      future.then((T value) {
        remaining--;
        List<T?>? valueList = values;
        if (valueList != null) {
          valueList[pos] = value;
          if (remaining == 0) {
            _future._completeWithValue(List<T>.from(valueList));
          }
        } else {
          if (cleanUp != null && value != null) {
            // Ensure errors from cleanUp are uncaught.
            new Future.sync(() {
              cleanUp(value);
            });
          }
          if (remaining == 0 && !eagerError) {
            // If eagerError is false, and valueList is null, then
            // error and stackTrace have been set in handleError above.
            _future._completeError(error, stackTrace);
          }
        }
      }, onError: handleError);
      // Increment the 'remaining' after the call to 'then'.
      // If that call throws, we don't expect any future callback from
      // the future, and we also don't increment remaining.
      remaining++;
    }
    if (remaining == 0) {
      return _future.._completeWithValue(<T>[]);
    }
    values = new List<T?>.filled(remaining, null);
  } catch (e, st) {
    // The error must have been thrown while iterating over the futures
    // list, or while installing a callback handler on the future.
    // This is a breach of the `Future` protocol, but we try to handle it
    // gracefully.
    if (remaining == 0 || eagerError) {
      // Throw a new Future.error.
      // Don't just call `_future._completeError` since that would propagate
      // the error too eagerly, not giving the callers time to install
      // error handlers.
      // Also, don't use `_asyncCompleteError` since that one doesn't give
      // zones the chance to intercept the error.
      return new Future.error(e, st);
    } else {
      // Don't allocate a list for values, thus indicating that there was an
      // error.
      // Set error to the caught exception.
      error = e;
      stackTrace = st;
    }
  }
  return _future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/wait.html>
:::
