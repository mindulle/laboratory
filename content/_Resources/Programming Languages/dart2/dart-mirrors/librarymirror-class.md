[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

LibraryMirror class
===================

A [LibraryMirror](librarymirror-class) reflects a Dart language library,
providing access to the variables, functions, and classes of the
library.

Implemented types

:   -   [DeclarationMirror](declarationmirror-class)
    -   [ObjectMirror](objectmirror-class)

Constructors
------------

[LibraryMirror](librarymirror/librarymirror)()

Properties {#instance-properties}
----------

[declarations](librarymirror/declarations) →
[Map](../dart-core/map-class)\<[Symbol](../dart-core/symbol-class),
[DeclarationMirror](declarationmirror-class)\>

::: {.features}
read-only
:::

Returns an immutable map of the declarations actually given in the
library.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

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

[libraryDependencies](librarymirror/librarydependencies) →
[List](../dart-core/list-class)\<[LibraryDependencyMirror](librarydependencymirror-class)\>

::: {.features}
read-only
:::

Returns a list of the imports and exports in this library;

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

[uri](librarymirror/uri) → [Uri](../dart-core/uri-class)

::: {.features}
read-only
:::

The absolute uri of the library.

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
==](librarymirror/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this mirror is equal to `other`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/LibraryMirror-class.html>
:::
