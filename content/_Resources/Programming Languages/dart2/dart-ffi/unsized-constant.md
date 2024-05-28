[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

unsized top-level constant
==========================

::: {.section .multi-line-signature}
[Unsized](unsized-class) const unsized
:::

This [NativeType](nativetype-class) does not have predefined size.

Unsized NativeTypes do not support [sizeOf](sizeof) because their size
is unknown. Consequently, [Pointer.elementAt](pointer/elementat) is not
available.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const unsized = const Unsized();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/unsized-constant.html>
:::
