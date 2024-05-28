[dart:async](../../dart-async/dart-async-library){._links-link}

bindBinaryCallbackGuarded\<T1, T2\> method
==========================================

::: {.section .multi-line-signature}
void Function(T1, T2) bindBinaryCallbackGuarded\<T1, T2\>(

1.  void callback(
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
 return (arg1, arg2) => this.runBinaryGuarded(registered, arg1, arg2);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void Function(T1, T2) bindBinaryCallbackGuarded<T1, T2>(
    void callback(T1 argument1, T2 argument2));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/bindBinaryCallbackGuarded.html>
:::
