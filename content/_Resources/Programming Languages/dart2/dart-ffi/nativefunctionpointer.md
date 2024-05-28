[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

NativeFunctionPointer\<NF extends Function\> extension
======================================================

Extension on [Pointer](pointer-class) specialized for the type argument
[NativeFunction](nativefunction-class).

on

:   -   [Pointer](pointer-class)\<[NativeFunction](nativefunction-class)\<NF\>\>

Methods {#instance-methods}
-------

[asFunction](nativefunctionpointer/asfunction)\<@[DartRepresentationOf](dartrepresentationof-class)(\'NF\') DF extends [Function](../dart-core/function-class)\>({[bool](../dart-core/bool-class) isLeaf = false}) → DF
:   Convert to Dart function, automatically marshalling the arguments
    and return value.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeFunctionPointer.html>
:::
