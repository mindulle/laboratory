[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

nullptr top-level property
==========================

::: {.section .multi-line-signature}
[Pointer](pointer-class)\<Never\> nullptr

::: {.features}
final
:::
:::

Represents a pointer into the native C memory corresponding to \'NULL\',
e.g. a pointer with address 0.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final Pointer<Never> nullptr = Pointer.fromAddress(0);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/nullptr.html>
:::
