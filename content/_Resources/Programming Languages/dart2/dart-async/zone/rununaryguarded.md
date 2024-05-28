[dart:async](../../dart-async/dart-async-library){._links-link}

runUnaryGuarded\<T\> method
===========================

::: {.section .multi-line-signature}
void runUnaryGuarded\<T\>(

1.  void action(
    1.  T argument

    ),
2.  T argument

)
:::

Executes the given `action` with `argument` in this zone and catches
synchronous errors.

See [runGuarded](runguarded).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void runUnaryGuarded<T>(void action(T argument), T argument);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/runUnaryGuarded.html>
:::
