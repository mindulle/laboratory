[dart:async](../../dart-async/dart-async-library){._links-link}

createTimer method
==================

::: {.section .multi-line-signature}
[Timer](../timer-class) createTimer(

1.  [Duration](../../dart-core/duration-class) duration,
2.  void callback( )

)
:::

Creates a [Timer](../timer-class) where the callback is executed in this
zone.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Timer createTimer(Duration duration, void Function() callback);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/createTimer.html>
:::
