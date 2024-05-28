[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

IsolateMirror class
===================

An [IsolateMirror](isolatemirror-class) reflects an isolate.

Implemented types

:   -   [Mirror](mirror-class)

Constructors
------------

[IsolateMirror](isolatemirror/isolatemirror)()

Properties {#instance-properties}
----------

[debugName](isolatemirror/debugname) →
[String](../dart-core/string-class)

::: {.features}
read-only
:::

A unique name used to refer to the isolate in debugging messages.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isCurrent](isolatemirror/iscurrent) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether this mirror reflects the currently running isolate.

[rootLibrary](isolatemirror/rootlibrary) →
[LibraryMirror](librarymirror-class)

::: {.features}
read-only
:::

The root library for the reflected isolate.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[loadUri](isolatemirror/loaduri)([Uri](../dart-core/uri-class) uri) →
[Future](../dart-async/future-class)\<[LibraryMirror](librarymirror-class)\>

Loads the library at the given uri into this isolate.

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
==](isolatemirror/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether `other` is an [IsolateMirror](isolatemirror-class) on the same
isolate as this mirror.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/IsolateMirror-class.html>
:::
