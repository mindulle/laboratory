[dart:async](../../dart-async/dart-async-library){._links-link}

Completer\<T\>.sync constructor
===============================

::: {.section .multi-line-signature}
Completer\<T\>.sync()
:::

Completes the future synchronously.

This constructor should be avoided unless the completion of the future
is known to be the final result of another asynchronous operation. If in
doubt use the default [Completer](../completer-class) constructor.

Using an normal, asynchronous, completer will never give the wrong
behavior, but using a synchronous completer incorrectly can cause
otherwise correct programs to break.

A synchronous completer is only intended for optimizing event
propagation when one asynchronous event immediately triggers another. It
should not be used unless the calls to [complete](complete) and
[completeError](completeerror) are guaranteed to occur in places where
it won\'t break `Future` invariants.

Completing synchronously means that the completer\'s future will be
completed immediately when calling the [complete](complete) or
[completeError](completeerror) method on a synchronous completer, which
also calls any callbacks registered on that future.

Completing synchronously must not break the rule that when you add a
callback on a future, that callback must not be called until the code
that added the callback has completed. For that reason, a synchronous
completion must only occur at the very end (in \"tail position\") of
another synchronous event, because at that point, completing the future
immediately is be equivalent to returning to the event loop and
completing the future in the next microtask.

Example:

``` {.language-dart data-language="dart"}
var completer = Completer.sync();
// The completion is the result of the asynchronous onDone event.
// No other operation is performed after the completion. It is safe
// to use the Completer.sync constructor.
stream.listen(print, onDone: () { completer.complete("done"); });
```

Bad example. Do not use this code. Only for illustrative purposes:

``` {.language-dart data-language="dart"}
var completer = Completer.sync();
completer.future.then((_) { bar(); });
// The completion is the result of the asynchronous onDone event.
// However, there is still code executed after the completion. This
// operation is *not* safe.
stream.listen(print, onDone: () {
  completer.complete("done");
  foo();  // In this case, foo() runs after bar().
});
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Completer.sync() => new _SyncCompleter<T>();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Completer/Completer.sync.html>
:::
