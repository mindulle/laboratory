[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Union class
===========

The supertype of all FFI union types.

FFI union types should extend this class and declare fields
corresponding to the underlying native union.

Field declarations in a [Union](union-class) subclass declaration are
automatically given a setter and getter implementation which accesses
the native union\'s field in memory.

All field declarations in a [Union](union-class) subclass declaration
must either have type [int](../dart-core/int-class) or
[double](../dart-core/double-class) and be annotated with a
[NativeType](nativetype-class) representing the native type, or must be
of type [Pointer](pointer-class). For example:

``` {.language-c data-language="dart"}
typedef union {
 int a;
 float b;
 void* c;
} my_union;
```

``` {.language-dart data-language="dart"}
class MyUnion extends Union {
  @Int32()
  external int a;

  @Float()
  external double b;

  external Pointer<Void> c;
}
```

All field declarations in a [Union](union-class) subclass declaration
must be marked `external`. You cannot create instances of the class,
only have it point to existing native memory, so there is no memory in
which to store non-native fields. External fields also cannot be
initialized by constructors since no Dart object is being created.

Instances of a subclass of [Union](union-class) have reference semantics
and are backed by native memory. The may allocated via allocation or
loaded from a [Pointer](pointer-class), but cannot be created by a
generative constructor.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   Union

Annotations

:   -   \@Since(\'2.14\')

Constructors
------------

[Union](union/union)()
:   Construct a reference to the [nullptr](nullptr).

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Union-class.html>
:::
