[dart:async](../../dart-async/dart-async-library){._links-link}

whenComplete method
===================

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> whenComplete(

1.  [FutureOr](../futureor-class)\<void\> action( )

)
:::

Registers a function to be called when this future completes.

The `action` function is called when this future completes, whether it
does so with a value or with an error.

This is the asynchronous equivalent of a \"finally\" block.

The future returned by this call, `f`, will complete the same way as
this future unless an error occurs in the `action` call, or in a
[Future](../future-class) returned by the `action` call. If the call to
`action` does not return a future, its return value is ignored.

If the call to `action` throws, then `f` is completed with the thrown
error.

If the call to `action` returns a [Future](../future-class), `f2`, then
completion of `f` is delayed until `f2` completes. If `f2` completes
with an error, that will be the result of `f` too. The value of `f2` is
always ignored.

This method is equivalent to:

``` {.language-dart data-language="dart"}
Future<T> whenComplete(action() {
  return this.then((v) {
    var f2 = action();
    if (f2 is Future) return f2.then((_) => v);
    return v;
  }, onError: (e) {
    var f2 = action();
    if (f2 is Future) return f2.then((_) { throw e; });
    throw e;
  });
}
```

Example:

``` {.language-dart data-language="dart"}
void main() async {
  var value =
      await waitTask().whenComplete(() => print('do something here'));
  // Prints "do something here" after waitTask() completed.
  print(value); // Prints "done"
}

Future<String> waitTask() {
  Future.delayed(const Duration(seconds: 5));
  return Future.value('done');
}
// Outputs: 'do some work here' after waitTask is completed.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> whenComplete(FutureOr<void> action());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/whenComplete.html>
:::
