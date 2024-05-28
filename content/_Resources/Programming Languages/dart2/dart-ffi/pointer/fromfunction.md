[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

fromFunction\<T extends Function\> method
=========================================

::: {.section .multi-line-signature}
[Pointer](../pointer-class)\<[NativeFunction](../nativefunction-class)\<T\>\>
fromFunction\<T extends Function\>(

1.  @[DartRepresentationOf](../dartrepresentationof-class)(\'T\')
    [Function](../../dart-core/function-class) f,
2.  \[[Object](../../dart-core/object-class)? exceptionalReturn\]

)
:::

Convert Dart function to a C function pointer, automatically marshalling
the arguments and return value

If an exception is thrown while calling `f()`, the native function will
return `exceptionalReturn`, which must be assignable to return type of
`f`.

The returned function address can only be invoked on the mutator (main)
thread of the current isolate. It will abort the process if invoked on
any other thread.

The pointer returned will remain alive for the duration of the current
isolate\'s lifetime. After the isolate it was created in is terminated,
invoking it from native code will cause undefined behavior.

Does not accept dynamic invocations \-- where the type of the receiver
is `dynamic`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Pointer<NativeFunction<T>> fromFunction<T extends Function>(
    @DartRepresentationOf('T') Function f,
    [Object? exceptionalReturn]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Pointer/fromFunction.html>
:::
