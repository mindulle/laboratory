[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

LibraryDependencyMirror class
=============================

A mirror on an import or export declaration.

Implemented types

:   -   [Mirror](mirror-class)

Constructors
------------

[LibraryDependencyMirror](librarydependencymirror/librarydependencymirror)()

Properties {#instance-properties}
----------

[combinators](librarydependencymirror/combinators) →
[List](../dart-core/list-class)\<[CombinatorMirror](combinatormirror-class)\>

::: {.features}
read-only
:::

Returns the list of show/hide combinators on the import/export
declaration.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isDeferred](librarydependencymirror/isdeferred) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Returns true iff this dependency is a deferred import. Otherwise returns
false.

[isExport](librarydependencymirror/isexport) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is `true` if this dependency is an export.

[isImport](librarydependencymirror/isimport) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Is `true` if this dependency is an import.

[location](librarydependencymirror/location) →
[SourceLocation](sourcelocation-class)?

::: {.features}
read-only
:::

Returns the source location for this import/export declaration.

[metadata](librarydependencymirror/metadata) →
[List](../dart-core/list-class)\<[InstanceMirror](instancemirror-class)\>

::: {.features}
read-only
:::

[prefix](librarydependencymirror/prefix) →
[Symbol](../dart-core/symbol-class)?

::: {.features}
read-only
:::

Returns the prefix if this is a prefixed import and `null` otherwise.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sourceLibrary](librarydependencymirror/sourcelibrary) →
[LibraryMirror](librarymirror-class)

::: {.features}
read-only
:::

Returns the library mirror of the library that imports or exports the
[targetLibrary](librarydependencymirror/targetlibrary).

[targetLibrary](librarydependencymirror/targetlibrary) →
[LibraryMirror](librarymirror-class)?

::: {.features}
read-only
:::

Returns the library mirror of the library that is imported or exported,
or null if the library is not loaded.

Methods {#instance-methods}
-------

[loadLibrary](librarydependencymirror/loadlibrary)() →
[Future](../dart-async/future-class)\<[LibraryMirror](librarymirror-class)\>

Returns a future that completes with a library mirror on the library
being imported or exported when it is loaded, and initiates a load of
that library if it is not loaded.

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
<https://api.dart.dev/stable/2.18.5/dart-mirrors/LibraryDependencyMirror-class.html>
:::
