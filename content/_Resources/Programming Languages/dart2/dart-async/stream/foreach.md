[dart:async](../../dart-async/dart-async-library){._links-link}

forEach method
==============

::: {.section .multi-line-signature}
[Future](../future-class) forEach(

1.  void action(
    1.  T element

    )

)
:::

Executes `action` on each element of this stream.

Completes the returned [Future](../future-class) when all elements of
this stream have been processed.

If this stream emits an error, or if the call to `action` throws, the
returned future completes with that error, and processing stops.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future forEach(void action(T element)) {
  _Future future = new _Future();
  StreamSubscription<T> subscription =
      this.listen(null, onError: future._completeError, onDone: () {
    future._complete(null);
  }, cancelOnError: true);
  subscription.onData((T element) {
    _runUserCode<void>(() => action(element), (_) {},
        _cancelAndErrorClosure(subscription, future));
  });
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/forEach.html>
:::
