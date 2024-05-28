[dart:async](../../dart-async/dart-async-library){._links-link}

bindUnaryCallbackGuarded\<T\> method
====================================

::: {.section .multi-line-signature}
void Function(T) bindUnaryCallbackGuarded\<T\>(

1.  void callback(
    1.  T argument

    )

)
:::

Registers the provided `callback` and returns a function that will
execute in this zone.

When the function executes, errors are caught and treated as uncaught
errors.

Equivalent to:

``` {.language-dart data-language="dart"}
ZoneCallback registered = this.registerUnaryCallback(callback);
return (arg) => this.runUnaryGuarded(registered, arg);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void Function(T) bindUnaryCallbackGuarded<T>(void callback(T argument));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/bindUnaryCallbackGuarded.html>
:::
