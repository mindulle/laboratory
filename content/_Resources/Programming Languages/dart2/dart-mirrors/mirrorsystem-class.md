[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

MirrorSystem class
==================

A [MirrorSystem](mirrorsystem-class) is the main interface used to
reflect on a set of associated libraries.

At runtime each running isolate has a distinct
[MirrorSystem](mirrorsystem-class).

It is also possible to have a [MirrorSystem](mirrorsystem-class) which
represents a set of libraries which are not running \-- perhaps at
compile-time. In this case, all available reflective functionality would
be supported, but runtime functionality (such as invoking a function or
inspecting the contents of a variable) would fail dynamically.

Constructors
------------

[MirrorSystem](mirrorsystem/mirrorsystem)()

Properties {#instance-properties}
----------

[dynamicType](mirrorsystem/dynamictype) → [TypeMirror](typemirror-class)

::: {.features}
read-only
:::

A mirror on the `dynamic` type.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isolate](mirrorsystem/isolate) → [IsolateMirror](isolatemirror-class)

::: {.features}
read-only
:::

A mirror on the isolate associated with this
[MirrorSystem](mirrorsystem-class).

[libraries](mirrorsystem/libraries) →
[Map](../dart-core/map-class)\<[Uri](../dart-core/uri-class),
[LibraryMirror](librarymirror-class)\>

::: {.features}
read-only
:::

All libraries known to the mirror system, indexed by their URI.

[neverType](mirrorsystem/nevertype) → [TypeMirror](typemirror-class)

::: {.features}
\@Since(\"2.8\"), read-only
:::

A mirror on the `Never` type.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[voidType](mirrorsystem/voidtype) → [TypeMirror](typemirror-class)

::: {.features}
read-only
:::

A mirror on the `void` type.

Methods {#instance-methods}
-------

[findLibrary](mirrorsystem/findlibrary)([Symbol](../dart-core/symbol-class)
libraryName) → [LibraryMirror](librarymirror-class)

Returns the unique library named `libraryName` if it exists.

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

Static Methods
--------------

[getName](mirrorsystem/getname)([Symbol](../dart-core/symbol-class) symbol) → [String](../dart-core/string-class)
:   Returns the name of `symbol`.

[getSymbol](mirrorsystem/getsymbol)([String](../dart-core/string-class) name, \[[LibraryMirror](librarymirror-class)? library\]) → [Symbol](../dart-core/symbol-class)
:   Returns a symbol for `name`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorSystem-class.html>
:::
