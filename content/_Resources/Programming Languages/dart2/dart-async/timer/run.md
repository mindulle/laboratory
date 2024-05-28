[dart:async](../../dart-async/dart-async-library){._links-link}

run method
==========

::: {.section .multi-line-signature}
void run(

1.  void callback( )

)
:::

Runs the given `callback` asynchronously as soon as possible.

This function is equivalent to `new Timer(Duration.zero, callback)`.

Example:

``` {.language-dart data-language="dart"}
Timer.run(() => print('timer run'));
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void run(void Function() callback) {
  new Timer(Duration.zero, callback);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Timer/run.html>
:::
