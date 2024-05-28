[dart:io](../dart-io/dart-io-library){._links-link}

Link class
==========

References to filesystem links.

Implemented types

:   -   [FileSystemEntity](filesystementity-class)

Constructors
------------

[Link](link/link)([String](../dart-core/string-class) path)

::: {.constructor-modifier .features}
factory
:::

Creates a Link object.

[Link.fromRawPath](link/link.fromrawpath)([Uint8List](../dart-typed_data/uint8list-class)
rawPath)

::: {.constructor-modifier .features}
factory
:::

[Link.fromUri](link/link.fromuri)([Uri](../dart-core/uri-class) uri)

::: {.constructor-modifier .features}
factory
:::

Creates a [Link](link-class) object.

Properties {#instance-properties}
----------

[absolute](link/absolute) → [Link](link-class)

::: {.features}
read-only, override
:::

A [Link](link-class) instance whose path is the absolute path to
[this](link-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isAbsolute](filesystementity/isabsolute) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this object\'s path is absolute.

[parent](filesystementity/parent) → [Directory](directory-class)

::: {.features}
read-only, inherited
:::

The parent directory of this entity.

[path](filesystementity/path) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[uri](filesystementity/uri) → [Uri](../dart-core/uri-class)

::: {.features}
read-only, inherited
:::

A [Uri](../dart-core/uri-class) representing the file system entity\'s
location.

Methods {#instance-methods}
-------

[create](link/create)([String](../dart-core/string-class) target,
{[bool](../dart-core/bool-class) recursive = false}) →
[Future](../dart-async/future-class)\<[Link](link-class)\>

Creates a symbolic link in the file system.

[createSync](link/createsync)([String](../dart-core/string-class)
target, {[bool](../dart-core/bool-class) recursive = false}) → void

Synchronously create the link. Calling [createSync](link/createsync) on
an existing link will throw an exception.

[delete](filesystementity/delete)({[bool](../dart-core/bool-class)
recursive = false}) →
[Future](../dart-async/future-class)\<[FileSystemEntity](filesystementity-class)\>

::: {.features}
inherited
:::

Deletes this `FileSystemEntity`.

[deleteSync](filesystementity/deletesync)({[bool](../dart-core/bool-class)
recursive = false}) → void

::: {.features}
inherited
:::

Synchronously deletes this [FileSystemEntity](filesystementity-class).

[exists](filesystementity/exists)() →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether the file system entity with this path exists.

[existsSync](filesystementity/existssync)() →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Synchronously checks whether the file system entity with this path
exists.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[rename](link/rename)([String](../dart-core/string-class) newPath) →
[Future](../dart-async/future-class)\<[Link](link-class)\>

::: {.features}
override
:::

Renames this link.

[renameSync](link/renamesync)([String](../dart-core/string-class)
newPath) → [Link](link-class)

::: {.features}
override
:::

Synchronously renames this link.

[resolveSymbolicLinks](link/resolvesymboliclinks)() →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
override
:::

Resolves the path of a file system object relative to the current
working directory.

[resolveSymbolicLinksSync](link/resolvesymboliclinkssync)() →
[String](../dart-core/string-class)

::: {.features}
override
:::

Resolves the path of a file system object relative to the current
working directory.

[stat](filesystementity/stat)() →
[Future](../dart-async/future-class)\<[FileStat](filestat-class)\>

::: {.features}
inherited
:::

Calls the operating system\'s `stat()` function on
[path](filesystementity/path).

[statSync](filesystementity/statsync)() → [FileStat](filestat-class)

::: {.features}
inherited
:::

Synchronously calls the operating system\'s `stat()` function on
[path](filesystementity/path).

[target](link/target)() →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

Gets the target of the link.

[targetSync](link/targetsync)() → [String](../dart-core/string-class)

Synchronously gets the target of the link.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](link/update)([String](../dart-core/string-class) target) →
[Future](../dart-async/future-class)\<[Link](link-class)\>

Updates the link.

[updateSync](link/updatesync)([String](../dart-core/string-class)
target) → void

Synchronously updates the link.

[watch](filesystementity/watch)({[int](../dart-core/int-class) events =
FileSystemEvent.all, [bool](../dart-core/bool-class) recursive = false})
→
[Stream](../dart-async/stream-class)\<[FileSystemEvent](filesystemevent-class)\>

::: {.features}
inherited
:::

Start watching the [FileSystemEntity](filesystementity-class) for
changes.

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
<https://api.dart.dev/stable/2.18.5/dart-io/Link-class.html>
:::
