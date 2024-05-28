[dart:io](../dart-io/dart-io-library){._links-link}

FileSystemEvent class
=====================

Base event class emitted by
[FileSystemEntity.watch](filesystementity/watch).

Implementers

:   -   [FileSystemCreateEvent](filesystemcreateevent-class)
    -   [FileSystemDeleteEvent](filesystemdeleteevent-class)
    -   [FileSystemModifyEvent](filesystemmodifyevent-class)
    -   [FileSystemMoveEvent](filesystemmoveevent-class)

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isDirectory](filesystemevent/isdirectory) →
[bool](../dart-core/bool-class)

::: {.features}
final
:::

Is `true` if the event target was a directory.

[path](filesystemevent/path) → [String](../dart-core/string-class)

::: {.features}
final
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
final
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

Constants
---------

[all](filesystemevent/all-constant) → const [int](../dart-core/int-class)
:   Bitfield for [FileSystemEntity.watch](filesystementity/watch), for
    enabling all of [create](filesystemevent/create-constant),
    [modify](filesystemevent/modify-constant),
    [delete](filesystemevent/delete-constant) and
    [move](filesystemevent/move-constant).
    <div>

    `create | modify | delete | move`

    </div>

[create](filesystemevent/create-constant) → const [int](../dart-core/int-class)
:   Bitfield for [FileSystemEntity.watch](filesystementity/watch), to
    enable [FileSystemCreateEvent](filesystemcreateevent-class)s.
    <div>

    `1 << 0`

    </div>

[delete](filesystemevent/delete-constant) → const [int](../dart-core/int-class)
:   Bitfield for [FileSystemEntity.watch](filesystementity/watch), to
    enable [FileSystemDeleteEvent](filesystemdeleteevent-class)s.
    <div>

    `1 << 2`

    </div>

[modify](filesystemevent/modify-constant) → const [int](../dart-core/int-class)
:   Bitfield for [FileSystemEntity.watch](filesystementity/watch), to
    enable [FileSystemModifyEvent](filesystemmodifyevent-class)s.
    <div>

    `1 << 1`

    </div>

[move](filesystemevent/move-constant) → const [int](../dart-core/int-class)
:   Bitfield for [FileSystemEntity.watch](filesystementity/watch), to
    enable [FileSystemMoveEvent](filesystemmoveevent-class)s.
    <div>

    `1 << 3`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEvent-class.html>
:::
