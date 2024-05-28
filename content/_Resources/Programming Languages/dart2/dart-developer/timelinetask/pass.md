[dart:developer](../../dart-developer/dart-developer-library){._links-link}

pass method
===========

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) pass()
:::

Retrieve the [TimelineTask](../timelinetask-class)\'s task id. Will
throw an exception if the stack is not empty.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int pass() {
  if (_stack.length > 0) {
    throw new StateError(
        'You cannot pass a TimelineTask without finishing all started '
        'operations');
  }
  int r = _taskId;
  return r;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/TimelineTask/pass.html>
:::
