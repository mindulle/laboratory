[dart:async](../../dart-async/dart-async-library){._links-link}

scheduleMicrotask method
========================

::: {.section .multi-line-signature}
void scheduleMicrotask(

1.  void callback( )

)
:::

Runs `callback` asynchronously in this zone.

The global `scheduleMicrotask` delegates to the [current](current)
zone\'s [scheduleMicrotask](schedulemicrotask). The root zone\'s
implementation interacts with the underlying system to schedule the
given callback as a microtask.

Custom zones may intercept this operation (for example to wrap the given
`callback`), or to implement their own microtask scheduler. In the
latter case, they will usually still use the parent zone\'s
[ZoneDelegate.scheduleMicrotask](../zonedelegate/schedulemicrotask) to
attach themselves to the existing event loop.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void scheduleMicrotask(void Function() callback);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/scheduleMicrotask.html>
:::
