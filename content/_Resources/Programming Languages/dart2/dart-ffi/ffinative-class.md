[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

FfiNative\<T\> class
====================

Annotation to be used for marking an external function as FFI native.

Example:

``` {.language-dart data-language="dart"}
@FfiNative<Int64 Function(Int64, Int64)>('FfiNative_Sum', isLeaf:true)
external int sum(int a, int b);
```

Calling such functions will throw an exception if no resolver was set on
the library or the resolver failed to resolve the name.

See `Dart_SetFfiNativeResolver` in `dart_api.h`

NOTE: This is an experimental feature and may change in the future.

Annotations

:   -   \@Since(\'2.14\')

Constructors
------------

[FfiNative](ffinative/ffinative)([String](../dart-core/string-class)
nativeName, {[bool](../dart-core/bool-class) isLeaf = false})

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isLeaf](ffinative/isleaf) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

[nativeName](ffinative/nativename) → [String](../dart-core/string-class)

::: {.features}
final
:::

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/FfiNative-class.html>
:::
