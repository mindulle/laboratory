[dart:async](../../dart-async/dart-async-library){._links-link}

Completer\<T\> constructor
==========================

::: {.section .multi-line-signature}
Completer\<T\>()
:::

Creates a new completer.

The general workflow for creating a new future is to 1) create a new
completer, 2) hand out its future, and, at a later point, 3) invoke
either [complete](complete) or [completeError](completeerror).

The completer completes the future asynchronously. That means that
callbacks registered on the future are not called immediately when
[complete](complete) or [completeError](completeerror) is called.
Instead the callbacks are delayed until a later microtask.

Example:

``` {.language-dart data-language="dart"}
var completer = new Completer();
handOut(completer.future);
later: {
  completer.complete('completion value');
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Completer() => new _AsyncCompleter<T>();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Completer/Completer.html>
:::
