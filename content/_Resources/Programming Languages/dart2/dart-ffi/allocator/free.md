[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

free method
===========

::: {.section .multi-line-signature}
void free(

1.  [Pointer](../pointer-class)\<[NativeType](../nativetype-class)\>
    pointer

)
:::

Releases memory allocated on the native heap.

Throws an [ArgumentError](../../dart-core/argumenterror-class) if the
memory pointed to by `pointer` cannot be freed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void free(Pointer pointer);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Allocator/free.html>
:::
