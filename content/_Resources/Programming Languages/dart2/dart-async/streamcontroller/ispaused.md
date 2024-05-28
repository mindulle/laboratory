[dart:async](../../dart-async/dart-async-library){._links-link}

isPaused property
=================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isPaused
:::

Whether the subscription would need to buffer events.

This is the case if the controller\'s stream has a listener and it is
paused, or if it has not received a listener yet. In that case, the
controller is considered paused as well.

A broadcast stream controller is never considered paused. It always
forwards its events to all uncanceled subscriptions, if any, and let the
subscriptions handle their own pausing and buffering.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isPaused;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/isPaused.html>
:::
