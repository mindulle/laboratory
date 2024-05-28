[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

ObjectMirror class
==================

An [ObjectMirror](objectmirror-class) is a common superinterface of
[InstanceMirror](instancemirror-class),
[ClassMirror](classmirror-class), and
[LibraryMirror](librarymirror-class) that represents their shared
functionality.

For the purposes of the mirrors library, these types are all
object-like, in that they support method invocation and field access.
Real Dart objects are represented by the
[InstanceMirror](instancemirror-class) type.

See [InstanceMirror](instancemirror-class),
[ClassMirror](classmirror-class), and
[LibraryMirror](librarymirror-class).

Implemented types

:   -   [Mirror](mirror-class)

Implementers

:   -   [ClassMirror](classmirror-class)
    -   [InstanceMirror](instancemirror-class)
    -   [LibraryMirror](librarymirror-class)

Constructors
------------

[ObjectMirror](objectmirror/objectmirror)()

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

[delegate](objectmirror/delegate)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

Performs `invocation` on the reflectee of this
[ObjectMirror](objectmirror-class).

[getField](objectmirror/getfield)([Symbol](../dart-core/symbol-class)
fieldName) → [InstanceMirror](instancemirror-class)

Invokes a getter and returns a mirror on the result.

[invoke](objectmirror/invoke)([Symbol](../dart-core/symbol-class)
memberName, [List](../dart-core/list-class) positionalArguments,
\[[Map](../dart-core/map-class)\<[Symbol](../dart-core/symbol-class),
dynamic\> namedArguments = const \<Symbol, dynamic\>{}\]) →
[InstanceMirror](instancemirror-class)

Invokes the named function and returns a mirror on the result.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setField](objectmirror/setfield)([Symbol](../dart-core/symbol-class)
fieldName, dynamic value) → [InstanceMirror](instancemirror-class)

Invokes a setter and returns a mirror on the result.

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
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ObjectMirror-class.html>
:::
