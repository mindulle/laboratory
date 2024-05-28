[dart:developer](../../dart-developer/dart-developer-library){._links-link}

finishSync method
=================

::: {.section .multi-line-signature}
void finishSync()
:::

Finish the last synchronous operation that was started.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void finishSync() {
  if (!_hasTimeline) {
    return;
  }
  if (_stack.isEmpty) {
    throw new StateError('Uneven calls to startSync and finishSync');
  }
  // Pop top item off of stack.
  var block = _stack.removeLast();
  if (block == null) {
    // Dart stream was disabled when startSync was called.
    return;
  }
  // Finish it.
  block.finish();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Timeline/finishSync.html>
:::
