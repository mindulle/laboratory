[dart:async](../../dart-async/dart-async-library){._links-link}

runGuarded method
=================

::: {.section .multi-line-signature}
void runGuarded(

1.  void action( )

)
:::

Executes the given `action` in this zone and catches synchronous errors.

This function is equivalent to:

``` {.language-dart data-language="dart"}
try {
  this.run(action);
} catch (e, s) {
  this.handleUncaughtError(e, s);
}
```

See [run](run).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void runGuarded(void action());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/runGuarded.html>
:::
