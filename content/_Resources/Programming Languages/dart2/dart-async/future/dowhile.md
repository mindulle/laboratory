[dart:async](../../dart-async/dart-async-library){._links-link}

doWhile method
==============

::: {.section .multi-line-signature}
[Future](../future-class) doWhile(

1.  [FutureOr](../futureor-class)\<[bool](../../dart-core/bool-class)\>
    action( )

)
:::

Performs an operation repeatedly until it returns `false`.

The operation, `action`, may be either synchronous or asynchronous.

The operation is called repeatedly as long as it returns either the
[bool](../../dart-core/bool-class) value `true` or a `Future<bool>`
which completes with the value `true`.

If a call to `action` returns `false` or a [Future](../future-class)
that completes to `false`, iteration ends and the future returned by
[doWhile](dowhile) is completed with a `null` value.

If a call to `action` throws or a future returned by `action` completes
with an error, iteration ends and the future returned by
[doWhile](dowhile) completes with the same error.

Calls to `action` may happen at any time, including immediately after
calling `doWhile`. The only restriction is a new call to `action` won\'t
happen before the previous call has returned, and if it returned a
`Future<bool>`, not until that future has completed.

Example:

``` {.language-dart data-language="dart"}
void main() async {
  var value = 0;
  await Future.doWhile(() async {
    value++;
    await Future.delayed(const Duration(seconds: 1));
    if (value == 3) {
      print('Finished with $value');
      return false;
    }
    return true;
  });
}
// Outputs: 'Finished with 3'
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future doWhile(FutureOr<bool> action()) {
  _Future<void> doneSignal = new _Future<void>();
  late void Function(bool) nextIteration;
  // Bind this callback explicitly so that each iteration isn't bound in the
  // context of all the previous iterations' callbacks.
  // This avoids, e.g., deeply nested stack traces from the stack trace
  // package.
  nextIteration = Zone.current.bindUnaryCallbackGuarded((bool keepGoing) {
    while (keepGoing) {
      FutureOr<bool> result;
      try {
        result = action();
      } catch (error, stackTrace) {
        // Cannot use _completeWithErrorCallback because it completes
        // the future synchronously.
        _asyncCompleteWithErrorCallback(doneSignal, error, stackTrace);
        return;
      }
      if (result is Future<bool>) {
        result.then(nextIteration, onError: doneSignal._completeError);
        return;
      }
      // TODO(40014): Remove cast when type promotion works.
      keepGoing = result as bool;
    }
    doneSignal._complete(null);
  });
  nextIteration(true);
  return doneSignal;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/doWhile.html>
:::
