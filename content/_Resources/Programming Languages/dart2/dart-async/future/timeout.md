[dart:async](../../dart-async/dart-async-library){._links-link}

timeout method
==============

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> timeout(

1.  [Duration](../../dart-core/duration-class) timeLimit,
2.  {[FutureOr](../futureor-class)\<T\> onTimeout( )?}

)
:::

Time-out the future computation after `timeLimit` has passed.

Returns a new future that completes with the same value as this future,
if this future completes in time.

If this future does not complete before `timeLimit` has passed, the
`onTimeout` action is executed instead, and its result (whether it
returns or throws) is used as the result of the returned future. The
`onTimeout` function must return a `T` or a `Future<T>`.

If `onTimeout` is omitted, a timeout will cause the returned future to
complete with a [TimeoutException](../timeoutexception-class).

Example:

``` {.language-dart data-language="dart"}
void main() async {
  var result = await waitTask()
      .timeout(const Duration(seconds: 10));
  print(result); // 'completed'

  result = await waitTask()
      .timeout(const Duration(seconds: 1), onTimeout: () => 'timeout');
  print(result); // 'timeout'

  result = await waitTask()
      .timeout(const Duration(seconds: 2)); // Throws.
}

Future<String> waitTask() async {
  await Future.delayed(const Duration(seconds: 5));
  return 'completed';
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> timeout(Duration timeLimit, {FutureOr<T> onTimeout()?});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/timeout.html>
:::
