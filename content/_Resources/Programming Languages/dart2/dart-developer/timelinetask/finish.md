[dart:developer](../../dart-developer/dart-developer-library){._links-link}

finish method
=============

::: {.section .multi-line-signature}
void finish(

1.  {[Map](../../dart-core/map-class)? arguments}

)
:::

Finish the last synchronous operation that was started. Optionally takes
a [Map](../../dart-core/map-class) of `arguments`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void finish({Map? arguments}) {
  if (!_hasTimeline) {
    return;
  }
  if (_stack.length == 0) {
    throw new StateError('Uneven calls to start and finish');
  }
  if (_filterKey != null) {
    arguments ??= {};
    arguments[_kFilterKey] = _filterKey;
  }
  // Pop top item off of stack.
  var block = _stack.removeLast();
  if (block == null) {
    // Dart stream was disabled when start was called.
    return;
  }
  block._finish(arguments);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/TimelineTask/finish.html>
:::
