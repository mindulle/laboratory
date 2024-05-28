[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

InstanceMirror class
====================

An [InstanceMirror](instancemirror-class) reflects an instance of a Dart
language object.

Implemented types

:   -   [ObjectMirror](objectmirror-class)

Implementers

:   -   [ClosureMirror](closuremirror-class)

Constructors
------------

[InstanceMirror](instancemirror/instancemirror)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[hasReflectee](instancemirror/hasreflectee) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether [reflectee](instancemirror/reflectee) will return the instance
reflected by this mirror.

[reflectee](instancemirror/reflectee) → dynamic

::: {.features}
read-only
:::

If the [InstanceMirror](instancemirror-class) reflects an instance it is
meaningful to have a local reference to, we provide access to the actual
instance here.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[type](instancemirror/type) → [ClassMirror](classmirror-class)

::: {.features}
read-only
:::

A mirror on the type of the reflectee.

Methods {#instance-methods}
-------

[delegate](objectmirror/delegate)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Performs `invocation` on the reflectee of this
[ObjectMirror](objectmirror-class).

[getField](objectmirror/getfield)([Symbol](../dart-core/symbol-class)
fieldName) → [InstanceMirror](instancemirror-class)

::: {.features}
inherited
:::

Invokes a getter and returns a mirror on the result.

[invoke](objectmirror/invoke)([Symbol](../dart-core/symbol-class)
memberName, [List](../dart-core/list-class) positionalArguments,
\[[Map](../dart-core/map-class)\<[Symbol](../dart-core/symbol-class),
dynamic\> namedArguments = const \<Symbol, dynamic\>{}\]) →
[InstanceMirror](instancemirror-class)

::: {.features}
inherited
:::

Invokes the named function and returns a mirror on the result.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setField](objectmirror/setfield)([Symbol](../dart-core/symbol-class)
fieldName, dynamic value) → [InstanceMirror](instancemirror-class)

::: {.features}
inherited
:::

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
==](instancemirror/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this mirror is equal to `other`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/InstanceMirror-class.html>
:::
