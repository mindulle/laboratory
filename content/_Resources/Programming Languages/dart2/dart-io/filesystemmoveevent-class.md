[dart:io](../dart-io/dart-io-library){._links-link}

FileSystemMoveEvent class
=========================

File system event for moving of file system objects.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [FileSystemEvent](filesystemevent-class)
    -   FileSystemMoveEvent

Properties {#instance-properties}
----------

[destination](filesystemmoveevent/destination) →
[String](../dart-core/string-class)?

::: {.features}
final
:::

The destination path of the file being moved.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isDirectory](filesystemevent/isdirectory) →
[bool](../dart-core/bool-class)

::: {.features}
final, inherited
:::

Is `true` if the event target was a directory.

[path](filesystemevent/path) → [String](../dart-core/string-class)

::: {.features}
final, inherited
:::

The path that triggered the event.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[type](filesystemevent/type) → [int](../dart-core/int-class)

::: {.features}
final, inherited
:::

The type of event. See [FileSystemEvent](filesystemevent-class) for a
list of events.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](filesystemmoveevent/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
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
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemMoveEvent-class.html>
:::
