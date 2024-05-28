[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

TypedefMirror class
===================

A [TypedefMirror](typedefmirror-class) represents a typedef in a Dart
language program.

Implemented types

:   -   [TypeMirror](typemirror-class)

Constructors
------------

[TypedefMirror](typedefmirror/typedefmirror)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[hasReflectedType](typemirror/hasreflectedtype) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Returns true if this mirror reflects dynamic, a non-generic class or
typedef, or an instantiated generic class or typedef in the current
isolate. Otherwise, returns false.

[isOriginalDeclaration](typemirror/isoriginaldeclaration) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Is this the original declaration of this type?

[isPrivate](declarationmirror/isprivate) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this declaration is library private.

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

[originalDeclaration](typemirror/originaldeclaration) →
[TypeMirror](typemirror-class)

::: {.features}
read-only, inherited
:::

A mirror on the original declaration of this type.

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

[referent](typedefmirror/referent) →
[FunctionTypeMirror](functiontypemirror-class)

::: {.features}
read-only
:::

The defining type for this typedef.

[reflectedType](typemirror/reflectedtype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

If `hasReflectedType` returns true, returns the corresponding
[Type](../dart-core/type-class). Otherwise, an
[UnsupportedError](../dart-core/unsupportederror-class) is thrown.

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

[typeArguments](typemirror/typearguments) →
[List](../dart-core/list-class)\<[TypeMirror](typemirror-class)\>

::: {.features}
read-only, inherited
:::

An immutable list with mirrors for all type arguments for this type.

[typeVariables](typemirror/typevariables) →
[List](../dart-core/list-class)\<[TypeVariableMirror](typevariablemirror-class)\>

::: {.features}
read-only, inherited
:::

An immutable list with mirrors for all type variables for this type.

Methods {#instance-methods}
-------

[isAssignableTo](typemirror/isassignableto)([TypeMirror](typemirror-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks the assignability relationship, denoted by `<=>` in the language
specification.

[isSubtypeOf](typemirror/issubtypeof)([TypeMirror](typemirror-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks the subtype relationship, denoted by `<:` in the language
specification.

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
<https://api.dart.dev/stable/2.18.5/dart-mirrors/TypedefMirror-class.html>
:::
