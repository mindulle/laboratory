[dart:async](../../dart-async/dart-async-library){._links-link}

Future\<T\>.delayed constructor
===============================

::: {.section .multi-line-signature}
Future\<T\>.delayed(

1.  [Duration](../../dart-core/duration-class) duration,
2.  \[[FutureOr](../futureor-class)\<T\> computation( )?\]

)
:::

Creates a future that runs its computation after a delay.

The `computation` will be executed after the given `duration` has
passed, and the future is completed with the result of the computation.

If `computation` returns a future, the future returned by this
constructor will complete with the value or error of that future.

If the duration is 0 or less, it completes no sooner than in the next
event-loop iteration, after all microtasks have run.

If `computation` is omitted, it will be treated as if `computation` was
`() => null`, and the future will eventually complete with the `null`
value. In that case, `T` must be nullable.

If calling `computation` throws, the created future will complete with
the error.

See also [Completer](../completer-class) for a way to create and
complete a future at a later time that isn\'t necessarily after a known
fixed duration.

Example:

``` {.language-dart data-language="dart"}
Future.delayed(const Duration(seconds: 1), () {
  print('One second has passed.'); // Prints after 1 second.
});
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Future.delayed(Duration duration, [FutureOr<T> computation()?]) {
  if (computation == null && !typeAcceptsNull<T>()) {
    throw ArgumentError.value(
        null, "computation", "The type parameter is not nullable");
  }
  _Future<T> result = new _Future<T>();
  new Timer(duration, () {
    if (computation == null) {
      result._complete(null as T);
    } else {
      try {
        result._complete(computation());
      } catch (e, s) {
        _completeWithErrorCallback(result, e, s);
      }
    }
  });
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/Future.delayed.html>
:::
