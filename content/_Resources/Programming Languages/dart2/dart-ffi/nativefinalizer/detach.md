[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

detach method
=============

::: {.section .multi-line-signature}
void detach(

1.  [Object](../../dart-core/object-class) detach

)
:::

Detaches this finalizer from values attached with [detach](detach).

If this finalizer was attached multiple times to the same object with
different detachment keys, only those attachments which used
[detach](detach) are removed.

After detaching, an attachment won\'t cause any callbacks to happen if
the object become inaccessible.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void detach(Object detach);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeFinalizer/detach.html>
:::
