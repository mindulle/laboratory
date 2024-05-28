[dart:async](../../dart-async/dart-async-library){._links-link}

registerUnaryCallback\<R, T\> method
====================================

::: {.section .multi-line-signature}
[ZoneUnaryCallback](../zoneunarycallback)\<R, T\>
registerUnaryCallback\<R, T\>(

1.  R callback(
    1.  T arg

    )

)
:::

Registers the given callback in this zone.

Similar to [registerCallback](registercallback) but with a unary
callback.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZoneUnaryCallback<R, T> registerUnaryCallback<R, T>(R callback(T arg));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/registerUnaryCallback.html>
:::
