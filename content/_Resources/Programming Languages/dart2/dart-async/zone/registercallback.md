[dart:async](../../dart-async/dart-async-library){._links-link}

registerCallback\<R\> method
============================

::: {.section .multi-line-signature}
[ZoneCallback](../zonecallback)\<R\> registerCallback\<R\>(

1.  R callback( )

)
:::

Registers the given callback in this zone.

When implementing an asynchronous primitive that uses callbacks, the
callback must be registered using [registerCallback](registercallback)
at the point where the user provides the callback. This allows zones to
record other information that they need at the same time, perhaps even
wrapping the callback, so that the callback is prepared when it is later
run in the same zones (using [run](run)). For example, a zone may decide
to store the stack trace (at the time of the registration) with the
callback.

Returns the callback that should be used in place of the provided
`callback`. Frequently zones simply return the original callback.

Custom zones may intercept this operation. The default implementation in
[Zone.root](root-constant) returns the original callback unchanged.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZoneCallback<R> registerCallback<R>(R callback());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/registerCallback.html>
:::
