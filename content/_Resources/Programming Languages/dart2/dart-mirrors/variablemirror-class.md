[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

VariableMirror class
====================

A [VariableMirror](variablemirror-class) reflects a Dart language
variable declaration.

Implemented types

:   -   [DeclarationMirror](declarationmirror-class)

Implementers

:   -   [ParameterMirror](parametermirror-class)

Constructors
------------

[VariableMirror](variablemirror/variablemirror)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isConst](variablemirror/isconst) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Returns `true` if the reflectee is declared `const`. Otherwise returns
`false`.

[isExtensionMember](variablemirror/isextensionmember) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee an extension member?

[isFinal](variablemirror/isfinal) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Returns `true` if the reflectee is a final variable. Otherwise returns
`false`.

[isPrivate](declarationmirror/isprivate) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this declaration is library private.

[isStatic](variablemirror/isstatic) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Returns `true` if the reflectee is a static variable. Otherwise returns
`false`.

[isTopLevel](declarationmirror/istoplevel) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this declaration is top-level.

[location](declarationmirror/location) →
[SourceLocation](sourcelocation-class)?

::: {.features}
read-only, inherited
:::

The source location of this Dart language entity, or `null` if the
entity is synthetic.

[metadata](declarationmirror/metadata) →
[List](../dart-core/list-class)\<[InstanceMirror](instancemirror-class)\>

::: {.features}
read-only, inherited
:::

A list of the metadata associated with this declaration.

[owner](declarationmirror/owner) →
[DeclarationMirror](declarationmirror-class)?

::: {.features}
read-only, inherited
:::

A mirror on the owner of this Dart language entity.

[qualifiedName](declarationmirror/qualifiedname) →
[Symbol](../dart-core/symbol-class)

::: {.features}
read-only, inherited
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
read-only, inherited
:::

The simple name for this Dart language entity.

[type](variablemirror/type) → [TypeMirror](typemirror-class)

::: {.features}
read-only
:::

Returns a mirror on the type of the reflectee.

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
==](variablemirror/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this mirror is equal to `other`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/VariableMirror-class.html>
:::
