[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

NativeApi class
===============

Utilities for accessing the Dart VM API from Dart code or from C code
via `dart_api_dl.h`.

Annotations

:   -   \@Since(\'2.8\')

Constructors
------------

[NativeApi](nativeapi/nativeapi)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Properties
-----------------

[closeNativePort](nativeapi/closenativeport) →
[Pointer](pointer-class)\<[NativeFunction](nativefunction-class)\<[Int8](int8-class)
Function([Int64](int64-class))\>\>

::: {.features}
read-only
:::

A function pointer to
`bool Dart_CloseNativePort(Dart_Port native_port_id)` in
`dart_native_api.h`.

[initializeApiDLData](nativeapi/initializeapidldata) →
[Pointer](pointer-class)\<[Void](void-class)\>

::: {.features}
\@Since(\'2.9\'), read-only
:::

Pass this to `Dart_InitializeApiDL` in your native code to enable using
the symbols in `dart_api_dl.h`.

[majorVersion](nativeapi/majorversion) → [int](../dart-core/int-class)

::: {.features}
\@Since(\'2.9\'), read-only
:::

On breaking changes the major version is increased.

[minorVersion](nativeapi/minorversion) → [int](../dart-core/int-class)

::: {.features}
\@Since(\'2.9\'), read-only
:::

On backwards compatible changes the minor version is increased.

[newNativePort](nativeapi/newnativeport) →
[Pointer](pointer-class)\<[NativeFunction](nativefunction-class)\<[Int64](int64-class)
Function([Pointer](pointer-class)\<[Uint8](uint8-class)\>,
[Pointer](pointer-class)\<[NativeFunction](nativefunction-class)\<[Dart\_NativeMessageHandler](dart_nativemessagehandler)\>\>,
[Int8](int8-class))\>\>

::: {.features}
read-only
:::

A function pointer to

[postCObject](nativeapi/postcobject) →
[Pointer](pointer-class)\<[NativeFunction](nativefunction-class)\<[Int8](int8-class)
Function([Int64](int64-class),
[Pointer](pointer-class)\<[Dart\_CObject](dart_cobject-class)\>)\>\>

::: {.features}
read-only
:::

A function pointer to
`bool Dart_PostCObject(Dart_Port port_id, Dart_CObject* message)` in
`dart_native_api.h`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeApi-class.html>
:::
