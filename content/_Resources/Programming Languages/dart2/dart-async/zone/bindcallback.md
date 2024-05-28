[dart:async](../../dart-async/dart-async-library){._links-link}

bindCallback\<R\> method
========================

::: {.section .multi-line-signature}
[ZoneCallback](../zonecallback)\<R\> bindCallback\<R\>(

1.  R callback( )

)
:::

Registers the provided `callback` and returns a function that will
execute in this zone.

Equivalent to:

``` {.language-dart data-language="dart"}
ZoneCallback registered = this.registerCallback(callback);
return () => this.run(registered);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZoneCallback<R> bindCallback<R>(R callback());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/bindCallback.html>
:::
