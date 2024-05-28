[dart:core](../../dart-core/dart-core-library){._links-link}

Finalizer\<T\> constructor
==========================

::: {.section .multi-line-signature}
Finalizer\<T\>(

1.  void callback(
    1.  T

    )

)
:::

Creates a finalizer with the given finalization callback.

The `callback` is bound to the current zone when the
[Finalizer](../finalizer-class) is created, and will run in that zone
when called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Finalizer(void Function(T) callback);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Finalizer/Finalizer.html>
:::
