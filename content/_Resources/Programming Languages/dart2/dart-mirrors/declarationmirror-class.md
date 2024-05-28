[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

DeclarationMirror class
=======================

A [DeclarationMirror](declarationmirror-class) reflects some entity
declared in a Dart program.

Implemented types

:   -   [Mirror](mirror-class)

Implementers

:   -   [LibraryMirror](librarymirror-class)
    -   [MethodMirror](methodmirror-class)
    -   [TypeMirror](typemirror-class)
    -   [VariableMirror](variablemirror-class)

Constructors
------------

[DeclarationMirror](declarationmirror/declarationmirror)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isPrivate](declarationmirror/isprivate) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether this declaration is library private.

[isTopLevel](declarationmirror/istoplevel) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether this declaration is top-level.

[location](declarationmirror/location) →
[SourceLocation](sourcelocation-class)?

::: {.features}
read-only
:::

The source location of this Dart language entity, or `null` if the
entity is synthetic.

[metadata](declarationmirror/metadata) →
[List](../dart-core/list-class)\<[InstanceMirror](instancemirror-class)\>

::: {.features}
read-only
:::

A list of the metadata associated with this declaration.

[owner](declarationmirror/owner) →
[DeclarationMirror](declarationmirror-class)?

::: {.features}
read-only
:::

A mirror on the owner of this Dart language entity.

[qualifiedName](declarationmirror/qualifiedname) →
[Symbol](../dart-core/symbol-class)

::: {.features}
read-only
:::

The fully-qualified name for this Dart language entity.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[simpleName](declarationmirror/simplename) →
[Symbol](../dart-core/symbol-class)

::: {.features}
read-only
:::

The simple name for this Dart language entity.

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
<https://api.dart.dev/stable/2.18.5/dart-mirrors/DeclarationMirror-class.html>
:::
