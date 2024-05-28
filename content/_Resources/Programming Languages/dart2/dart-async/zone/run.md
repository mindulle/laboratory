[dart:async](../../dart-async/dart-async-library){._links-link}

run\<R\> method
===============

::: {.section .multi-line-signature}
R run\<R\>(

1.  R action( )

)
:::

Executes `action` in this zone.

By default (as implemented in the [root](root-constant) zone), runs
`action` with [current](current) set to this zone.

If `action` throws, the synchronous exception is not caught by the
zone\'s error handler. Use [runGuarded](runguarded) to achieve that.

Since the root zone is the only zone that can modify the value of
[current](current), custom zones intercepting run should always delegate
to their parent zone. They may take actions before and after the call.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
R run<R>(R action());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/run.html>
:::
