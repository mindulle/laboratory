[dart:async](../../dart-async/dart-async-library){._links-link}

runBinaryGuarded\<T1, T2\> method
=================================

::: {.section .multi-line-signature}
void runBinaryGuarded\<T1, T2\>(

1.  void action(
    1.  T1 argument1,
    2.  T2 argument2

    ),
2.  T1 argument1,
3.  T2 argument2

)
:::

Executes the given `action` with `argument1` and `argument2` in this
zone and catches synchronous errors.

See [runGuarded](runguarded).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void runBinaryGuarded<T1, T2>(
    void action(T1 argument1, T2 argument2), T1 argument1, T2 argument2);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/runBinaryGuarded.html>
:::
