[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

MethodMirror class
==================

A [MethodMirror](methodmirror-class) reflects a Dart language function,
method, constructor, getter, or setter.

Implemented types

:   -   [DeclarationMirror](declarationmirror-class)

Constructors
------------

[MethodMirror](methodmirror/methodmirror)()

Properties {#instance-properties}
----------

[constructorName](methodmirror/constructorname) →
[Symbol](../dart-core/symbol-class)

::: {.features}
read-only
:::

The constructor name for named constructors and factory methods.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isAbstract](methodmirror/isabstract) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee abstract?

[isConstConstructor](methodmirror/isconstconstructor) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee a const constructor?

[isConstructor](methodmirror/isconstructor) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee a constructor?

[isExtensionMember](methodmirror/isextensionmember) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee an extension method?

[isFactoryConstructor](methodmirror/isfactoryconstructor) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee a factory constructor?

[isGenerativeConstructor](methodmirror/isgenerativeconstructor) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee a generative constructor?

[isGetter](methodmirror/isgetter) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee a getter?

[isOperator](methodmirror/isoperator) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee an operator?

[isPrivate](declarationmirror/isprivate) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this declaration is library private.

[isRedirectingConstructor](methodmirror/isredirectingconstructor) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee a redirecting constructor?

[isRegularMethod](methodmirror/isregularmethod) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee a regular function or method?

[isSetter](methodmirror/issetter) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is the reflectee a setter?

[isStatic](methodmirror/isstatic) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

A function is considered non-static iff it is permited to refer to
\'this\'.

[isSynthetic](methodmirror/issynthetic) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Returns true if the reflectee is synthetic, and returns false otherwise.

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

[parameters](methodmirror/parameters) →
[List](../dart-core/list-class)\<[ParameterMirror](parametermirror-class)\>

::: {.features}
read-only
:::

A list of mirrors on the parameters for the reflectee.

[qualifiedName](declarationmirror/qualifiedname) →
[Symbol](../dart-core/symbol-class)

::: {.features}
read-only, inherited
:::

The fully-qualified name for this Dart language entity.

[returnType](methodmirror/returntype) → [TypeMirror](typemirror-class)

::: {.features}
read-only
:::

A mirror on the return type for the reflectee.

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

[source](methodmirror/source) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

The source code for the reflectee, if available. Otherwise null.

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
==](methodmirror/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this mirror is equal to `other`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MethodMirror-class.html>
:::
