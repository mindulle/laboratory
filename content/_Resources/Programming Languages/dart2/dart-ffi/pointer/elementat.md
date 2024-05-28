[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

elementAt method
================

::: {.section .multi-line-signature}
[Pointer](../pointer-class)\<T\> elementAt(

1.  [int](../../dart-core/int-class) index

)
:::

Pointer arithmetic (takes element size into account).

This method must be invoked with a compile-time constant `T`.

Does not accept dynamic invocations \-- where the type of the receiver
is `dynamic`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Pointer<T> elementAt(int index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Pointer/elementAt.html>
:::
