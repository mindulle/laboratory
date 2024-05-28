[dart:async](../../dart-async/dart-async-library){._links-link}

registerBinaryCallback\<R, T1, T2\> method
==========================================

::: {.section .multi-line-signature}
[ZoneBinaryCallback](../zonebinarycallback)\<R, T1, T2\>
registerBinaryCallback\<R, T1, T2\>(

1.  [Zone](../zone-class) zone,
2.  R f(
    1.  T1 arg1,
    2.  T2 arg2

    )

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZoneBinaryCallback<R, T1, T2> registerBinaryCallback<R, T1, T2>(
    Zone zone, R f(T1 arg1, T2 arg2));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/ZoneDelegate/registerBinaryCallback.html>
:::
