[dart:async](../../dart-async/dart-async-library){._links-link}

bindCallbackGuarded method
==========================

::: {.section .multi-line-signature}
void Function() bindCallbackGuarded(

1.  void callback( )

)
:::

Registers the provided `callback` and returns a function that will
execute in this zone.

When the function executes, errors are caught and treated as uncaught
errors.

Equivalent to:

``` {.language-dart data-language="dart"}
ZoneCallback registered = this.registerCallback(callback);
return () => this.runGuarded(registered);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void Function() bindCallbackGuarded(void Function() callback);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/bindCallbackGuarded.html>
:::
