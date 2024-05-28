[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

ClosureMirror class
===================

A [ClosureMirror](closuremirror-class) reflects a closure.

A [ClosureMirror](closuremirror-class) provides the ability to execute
its reflectee and introspect its function.

Implemented types

:   -   [InstanceMirror](instancemirror-class)

Constructors
------------

[ClosureMirror](closuremirror/closuremirror)()

Properties {#instance-properties}
----------

[function](closuremirror/function) → [MethodMirror](methodmirror-class)

::: {.features}
read-only
:::

A mirror on the function associated with this closure.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[hasReflectee](instancemirror/hasreflectee) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether [reflectee](instancemirror/reflectee) will return the instance
reflected by this mirror.

[reflectee](instancemirror/reflectee) → dynamic

::: {.features}
read-only, inherited
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
read-only, inherited
:::

A mirror on the type of the reflectee.

Methods {#instance-methods}
-------

[apply](closuremirror/apply)([List](../dart-core/list-class)
positionalArguments,
\[[Map](../dart-core/map-class)\<[Symbol](../dart-core/symbol-class),
dynamic\> namedArguments = const \<Symbol, dynamic\>{}\]) →
[InstanceMirror](instancemirror-class)

Executes the closure and returns a mirror on the result.

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
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClosureMirror-class.html>
:::
