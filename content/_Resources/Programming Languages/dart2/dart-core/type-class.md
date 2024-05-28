[dart:core](../dart-core/dart-core-library){._links-link}

Type class
==========

Runtime representation of a type.

Type objects represent types. A type object can be created in several
ways:

-   By a *type literal*, a type name occurring as an expression, like
    `Type type = int;`, or a type variable occurring as an expression,
    like `Type type = T;`.
-   By reading the run-time type of an object, like
    `Type type = o.runtimeType;`.
-   Through `dart:mirrors`.

A type object is intended as an entry point for using `dart:mirrors`.
The only operations supported are comparing to other type objects for
equality, and converting it to a string for debugging.

Constructors
------------

[Type](type/type)()

Properties {#instance-properties}
----------

[hashCode](type/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

A hash code for the type which is compatible with
[operator==](type/operator_equals).

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](type/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns a string which represents the underlying type.

Operators
---------

[operator ==](type/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

Whether `other` is a [Type](type-class) instance representing an
equivalent type.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Type-class.html>
:::
