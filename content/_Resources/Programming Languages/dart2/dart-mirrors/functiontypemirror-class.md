[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

FunctionTypeMirror class
========================

A [FunctionTypeMirror](functiontypemirror-class) represents the type of
a function in the Dart language.

Implemented types

:   -   [ClassMirror](classmirror-class)

Constructors
------------

[FunctionTypeMirror](functiontypemirror/functiontypemirror)()

Properties {#instance-properties}
----------

[callMethod](functiontypemirror/callmethod) →
[MethodMirror](methodmirror-class)

::: {.features}
read-only
:::

A mirror on the `call` method for the reflectee.

[declarations](classmirror/declarations) →
[Map](../dart-core/map-class)\<[Symbol](../dart-core/symbol-class),
[DeclarationMirror](declarationmirror-class)\>

::: {.features}
read-only, inherited
:::

Returns an immutable map of the declarations actually given in the class
declaration.

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

[instanceMembers](classmirror/instancemembers) →
[Map](../dart-core/map-class)\<[Symbol](../dart-core/symbol-class),
[MethodMirror](methodmirror-class)\>

::: {.features}
read-only, inherited
:::

Returns a map of the methods, getters and setters of an instance of the
class.

[isAbstract](classmirror/isabstract) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Is the reflectee abstract?

[isEnum](classmirror/isenum) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Is the reflectee an enum?

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

[mixin](classmirror/mixin) → [ClassMirror](classmirror-class)

::: {.features}
read-only, inherited
:::

The mixin of this class.

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

[parameters](functiontypemirror/parameters) →
[List](../dart-core/list-class)\<[ParameterMirror](parametermirror-class)\>

::: {.features}
read-only
:::

Returns a list of the parameter types of the reflectee.

[qualifiedName](declarationmirror/qualifiedname) →
[Symbol](../dart-core/symbol-class)

::: {.features}
read-only, inherited
:::

The fully-qualified name for this Dart language entity.

[reflectedType](typemirror/reflectedtype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

If `hasReflectedType` returns true, returns the corresponding
[Type](../dart-core/type-class). Otherwise, an
[UnsupportedError](../dart-core/unsupportederror-class) is thrown.

[returnType](functiontypemirror/returntype) →
[TypeMirror](typemirror-class)

::: {.features}
read-only
:::

Returns the return type of the reflectee.

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

[staticMembers](classmirror/staticmembers) →
[Map](../dart-core/map-class)\<[Symbol](../dart-core/symbol-class),
[MethodMirror](methodmirror-class)\>

::: {.features}
read-only, inherited
:::

Returns a map of the static methods, getters and setters of the class.

[superclass](classmirror/superclass) → [ClassMirror](classmirror-class)?

::: {.features}
read-only, inherited
:::

A mirror on the superclass on the reflectee.

[superinterfaces](classmirror/superinterfaces) →
[List](../dart-core/list-class)\<[ClassMirror](classmirror-class)\>

::: {.features}
read-only, inherited
:::

A list of mirrors on the superinterfaces of the reflectee.

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

[isAssignableTo](typemirror/isassignableto)([TypeMirror](typemirror-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks the assignability relationship, denoted by `<=>` in the language
specification.

[isSubclassOf](classmirror/issubclassof)([ClassMirror](classmirror-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns whether the class denoted by the receiver is a subclass of the
class denoted by the argument.

[isSubtypeOf](typemirror/issubtypeof)([TypeMirror](typemirror-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks the subtype relationship, denoted by `<:` in the language
specification.

[newInstance](classmirror/newinstance)([Symbol](../dart-core/symbol-class)
constructorName, [List](../dart-core/list-class) positionalArguments,
\[[Map](../dart-core/map-class)\<[Symbol](../dart-core/symbol-class),
dynamic\> namedArguments = const \<Symbol, dynamic\>{}\]) →
[InstanceMirror](instancemirror-class)

::: {.features}
inherited
:::

Invokes the named constructor and returns a mirror on the result.

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
<https://api.dart.dev/stable/2.18.5/dart-mirrors/FunctionTypeMirror-class.html>
:::
