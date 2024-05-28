[dart:io](../dart-io/dart-io-library){._links-link}

FileStat class
==============

The result of calling the POSIX `stat()` function on a file system
object.

This is an immutable object, representing the snapshotted values
returned by the `stat()` call.

Properties {#instance-properties}
----------

[accessed](filestat/accessed) → [DateTime](../dart-core/datetime-class)

::: {.features}
final
:::

The time of the last access to the data of the file system object.

[changed](filestat/changed) → [DateTime](../dart-core/datetime-class)

::: {.features}
final
:::

The time of the last change to the data or metadata of the file system
object.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[mode](filestat/mode) → [int](../dart-core/int-class)

::: {.features}
final
:::

The mode of the file system object.

[modified](filestat/modified) → [DateTime](../dart-core/datetime-class)

::: {.features}
final
:::

The time of the last change to the data of the file system object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[size](filestat/size) → [int](../dart-core/int-class)

::: {.features}
final
:::

The size of the file system object.

[type](filestat/type) →
[FileSystemEntityType](filesystementitytype-class)

::: {.features}
final
:::

The type of the underlying file system object.

Methods {#instance-methods}
-------

[modeString](filestat/modestring)() →
[String](../dart-core/string-class)

The mode value as a human-readable string.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](filestat/tostring)() → [String](../dart-core/string-class)

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

Static Methods
--------------

[stat](filestat/stat)([String](../dart-core/string-class) path) → [Future](../dart-async/future-class)\<[FileStat](filestat-class)\>
:   Asynchronously calls the operating system\'s `stat()` function (or
    equivalent) on `path`.

[statSync](filestat/statsync)([String](../dart-core/string-class) path) → [FileStat](filestat-class)
:   Calls the operating system\'s `stat()` function (or equivalent) on
    `path`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileStat-class.html>
:::
