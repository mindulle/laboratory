[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

NativeFinalizer constructor
===========================

::: {.section .multi-line-signature}
NativeFinalizer(

1.  [Pointer](../pointer-class)\<[NativeFinalizerFunction](../nativefinalizerfunction)\>
    callback

)
:::

Creates a finalizer with the given finalization callback.

The `callback` must be a native function which can be executed outside
of a Dart isolate. This means that passing an FFI trampoline (a function
pointer obtained via [Pointer.fromFunction](../pointer/fromfunction)) is
not supported.

The `callback` might be invoked on an arbitrary thread and not necessary
on the same thread that created
[NativeFinalizer](../nativefinalizer-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// TODO(https://dartbug.com/47778): Implement isolate independent code and
// update the above comment.
external factory NativeFinalizer(Pointer<NativeFinalizerFunction> callback);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeFinalizer/NativeFinalizer.html>
:::
