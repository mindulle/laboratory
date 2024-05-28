[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

hashCode property
=================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) hashCode

::: {.features}
override
:::
:::

The hash code for a Pointer only depends on its address.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get hashCode {
  return address.hashCode;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Pointer/hashCode.html>
:::
