[dart:async](../../dart-async/dart-async-library){._links-link}

isCompleted property
====================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isCompleted
:::

Whether the [future](future) has been completed.

Reflects whether [complete](complete) or [completeError](completeerror)
has been called. A `true` value doesn\'t necessarily mean that listeners
of this future have been invoked yet, either because the completer
usually waits until a later microtask to propagate the result, or
because [complete](complete) was called with a future that hasn\'t
completed yet.

When this value is `true`, [complete](complete) and
[completeError](completeerror) must not be called again.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isCompleted;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Completer/isCompleted.html>
:::
