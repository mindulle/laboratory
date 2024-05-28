[dart:async](../../dart-async/dart-async-library){._links-link}

cancel method
=============

::: {.section .multi-line-signature}
void cancel()
:::

Cancels the timer.

Once a [Timer](../timer-class) has been canceled, the callback function
will not be called by the timer. Calling [cancel](cancel) more than once
on a [Timer](../timer-class) is allowed, and will have no further
effect.

Example:

``` {.language-dart data-language="dart"}
final timer =
    Timer(const Duration(seconds: 5), () => print('Timer finished'));
// Cancel timer, callback never called.
timer.cancel();
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void cancel();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Timer/cancel.html>
:::
