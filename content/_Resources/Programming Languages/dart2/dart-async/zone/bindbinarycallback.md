[dart:async](../../dart-async/dart-async-library){._links-link}

bindBinaryCallback\<R, T1, T2\> method
======================================

::: {.section .multi-line-signature}
[ZoneBinaryCallback](../zonebinarycallback)\<R, T1, T2\>
bindBinaryCallback\<R, T1, T2\>(

1.  R callback(
    1.  T1 argument1,
    2.  T2 argument2

    )

)
:::

Registers the provided `callback` and returns a function that will
execute in this zone.

Equivalent to:

``` {.language-dart data-language="dart"}
ZoneCallback registered = registerBinaryCallback(callback);
return (arg1, arg2) => this.runBinary(registered, arg1, arg2);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZoneBinaryCallback<R, T1, T2> bindBinaryCallback<R, T1, T2>(
    R callback(T1 argument1, T2 argument2));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/bindBinaryCallback.html>
:::
