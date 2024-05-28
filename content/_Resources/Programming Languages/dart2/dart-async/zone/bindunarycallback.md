[dart:async](../../dart-async/dart-async-library){._links-link}

bindUnaryCallback\<R, T\> method
================================

::: {.section .multi-line-signature}
[ZoneUnaryCallback](../zoneunarycallback)\<R, T\> bindUnaryCallback\<R,
T\>(

1.  R callback(
    1.  T argument

    )

)
:::

Registers the provided `callback` and returns a function that will
execute in this zone.

Equivalent to:

``` {.language-dart data-language="dart"}
ZoneCallback registered = this.registerUnaryCallback(callback);
return (arg) => this.runUnary(registered, arg);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZoneUnaryCallback<R, T> bindUnaryCallback<R, T>(R callback(T argument));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/bindUnaryCallback.html>
:::
