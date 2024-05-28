[dart:io](../dart-io/dart-io-library){._links-link}

IOOverrides class
=================

Facilities for overriding various APIs of `dart:io` with mock
implementations.

This abstract base class should be extended with overrides for the
operations needed to construct mocks. The implementations in this base
class default to the actual `dart:io` implementation. For example:

``` {.language-dart data-language="dart"}
class MyDirectory implements Directory {
  ...
  // An implementation of the Directory interface
  ...
}

void main() {
  IOOverrides.runZoned(() {
    ...
    // Operations will use MyDirectory instead of dart:io's Directory
    // implementation whenever Directory is used.
    ...
  }, createDirectory: (String path) => new MyDirectory(path));
}
```

Constructors
------------

[IOOverrides](iooverrides/iooverrides)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[stderr](iooverrides/stderr) → [Stdout](stdout-class)

::: {.features}
read-only
:::

The standard output stream of errors written by this program.

[stdin](iooverrides/stdin) → [Stdin](stdin-class)

::: {.features}
read-only
:::

The standard input stream of data read by this program.

[stdout](iooverrides/stdout) → [Stdout](stdout-class)

::: {.features}
read-only
:::

The standard output stream of data written by this program.

Methods {#instance-methods}
-------

[createDirectory](iooverrides/createdirectory)([String](../dart-core/string-class)
path) → [Directory](directory-class)

Creates a new [Directory](directory-class) object for the given `path`.

[createFile](iooverrides/createfile)([String](../dart-core/string-class)
path) → [File](file-class)

Creates a new [File](file-class) object for the given `path`.

[createLink](iooverrides/createlink)([String](../dart-core/string-class)
path) → [Link](link-class)

Returns a new [Link](link-class) object for the given `path`.

[fseGetType](iooverrides/fsegettype)([String](../dart-core/string-class)
path, [bool](../dart-core/bool-class) followLinks) →
[Future](../dart-async/future-class)\<[FileSystemEntityType](filesystementitytype-class)\>

Asynchronously returns the `FileSystemEntityType` for `path`.

[fseGetTypeSync](iooverrides/fsegettypesync)([String](../dart-core/string-class)
path, [bool](../dart-core/bool-class) followLinks) →
[FileSystemEntityType](filesystementitytype-class)

Returns the [FileSystemEntityType](filesystementitytype-class) for
`path`.

[fseIdentical](iooverrides/fseidentical)([String](../dart-core/string-class)
path1, [String](../dart-core/string-class) path2) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

Asynchronously returns `true` if `path1` and `path2` are paths to the
same file system object.

[fseIdenticalSync](iooverrides/fseidenticalsync)([String](../dart-core/string-class)
path1, [String](../dart-core/string-class) path2) →
[bool](../dart-core/bool-class)

Returns `true` if `path1` and `path2` are paths to the same file system
object.

[fsWatch](iooverrides/fswatch)([String](../dart-core/string-class) path,
[int](../dart-core/int-class) events, [bool](../dart-core/bool-class)
recursive) →
[Stream](../dart-async/stream-class)\<[FileSystemEvent](filesystemevent-class)\>

Returns a [Stream](../dart-async/stream-class) of `FileSystemEvent`s.

[fsWatchIsSupported](iooverrides/fswatchissupported)() →
[bool](../dart-core/bool-class)

Returns `true` when [FileSystemEntity.watch](filesystementity/watch) is
supported.

[getCurrentDirectory](iooverrides/getcurrentdirectory)() →
[Directory](directory-class)

Returns the current working directory.

[getSystemTempDirectory](iooverrides/getsystemtempdirectory)() →
[Directory](directory-class)

Returns the system temporary directory.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[serverSocketBind](iooverrides/serversocketbind)(dynamic address,
[int](../dart-core/int-class) port, {[int](../dart-core/int-class)
backlog = 0, [bool](../dart-core/bool-class) v6Only = false,
[bool](../dart-core/bool-class) shared = false}) →
[Future](../dart-async/future-class)\<[ServerSocket](serversocket-class)\>

Asynchronously returns a `ServerSocket` that connects to the given
address and port when successful.

[setCurrentDirectory](iooverrides/setcurrentdirectory)([String](../dart-core/string-class)
path) → void

Sets the current working directory to be `path`.

[socketConnect](iooverrides/socketconnect)(dynamic host,
[int](../dart-core/int-class) port, {dynamic sourceAddress,
[int](../dart-core/int-class) sourcePort = 0,
[Duration](../dart-core/duration-class)? timeout}) →
[Future](../dart-async/future-class)\<[Socket](socket-class)\>

Asynchronously returns a `Socket` connected to the given host and port.

[socketStartConnect](iooverrides/socketstartconnect)(dynamic host,
[int](../dart-core/int-class) port, {dynamic sourceAddress,
[int](../dart-core/int-class) sourcePort = 0}) →
[Future](../dart-async/future-class)\<[ConnectionTask](connectiontask-class)\<[Socket](socket-class)\>\>

Asynchronously returns a `ConnectionTask` that connects to the given
host and port when successful.

[stat](iooverrides/stat)([String](../dart-core/string-class) path) →
[Future](../dart-async/future-class)\<[FileStat](filestat-class)\>

Asynchronously returns `FileStat` information for `path`.

[statSync](iooverrides/statsync)([String](../dart-core/string-class)
path) → [FileStat](filestat-class)

Returns [FileStat](filestat-class) information for `path`.

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

Static Properties
-----------------

[current](iooverrides/current) → [IOOverrides](iooverrides-class)?

::: {.features}
read-only
:::

[global](iooverrides/global) ← [IOOverrides](iooverrides-class)?

::: {.features}
write-only
:::

The [IOOverrides](iooverrides-class) to use in the root
[Zone](../dart-async/zone-class).

Static Methods
--------------

[runWithIOOverrides](iooverrides/runwithiooverrides)\<R\>(R body(), [IOOverrides](iooverrides-class) overrides) → R
:   Runs `body` in a fresh [Zone](../dart-async/zone-class) using the
    overrides found in `overrides`.

[runZoned](iooverrides/runzoned)\<R\>(R body(), {[Directory](directory-class) createDirectory([String](../dart-core/string-class))?, [Directory](directory-class) getCurrentDirectory()?, void setCurrentDirectory([String](../dart-core/string-class))?, [Directory](directory-class) getSystemTempDirectory()?, [File](file-class) createFile([String](../dart-core/string-class))?, [Future](../dart-async/future-class)\<[FileStat](filestat-class)\> stat([String](../dart-core/string-class))?, [FileStat](filestat-class) statSync([String](../dart-core/string-class))?, [Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\> fseIdentical([String](../dart-core/string-class), [String](../dart-core/string-class))?, [bool](../dart-core/bool-class) fseIdenticalSync([String](../dart-core/string-class), [String](../dart-core/string-class))?, [Future](../dart-async/future-class)\<[FileSystemEntityType](filesystementitytype-class)\> fseGetType([String](../dart-core/string-class), [bool](../dart-core/bool-class))?, [FileSystemEntityType](filesystementitytype-class) fseGetTypeSync([String](../dart-core/string-class), [bool](../dart-core/bool-class))?, [Stream](../dart-async/stream-class)\<[FileSystemEvent](filesystemevent-class)\> fsWatch([String](../dart-core/string-class), [int](../dart-core/int-class), [bool](../dart-core/bool-class))?, [bool](../dart-core/bool-class) fsWatchIsSupported()?, [Link](link-class) createLink([String](../dart-core/string-class))?, [Future](../dart-async/future-class)\<[Socket](socket-class)\> socketConnect(dynamic, [int](../dart-core/int-class), {dynamic sourceAddress, [int](../dart-core/int-class) sourcePort, [Duration](../dart-core/duration-class)? timeout})?, [Future](../dart-async/future-class)\<[ConnectionTask](connectiontask-class)\<[Socket](socket-class)\>\> socketStartConnect(dynamic, [int](../dart-core/int-class), {dynamic sourceAddress, [int](../dart-core/int-class) sourcePort})?, [Future](../dart-async/future-class)\<[ServerSocket](serversocket-class)\> serverSocketBind(dynamic, [int](../dart-core/int-class), {[int](../dart-core/int-class) backlog, [bool](../dart-core/bool-class) shared, [bool](../dart-core/bool-class) v6Only})?, [Stdin](stdin-class) stdin()?, [Stdout](stdout-class) stdout()?, [Stdout](stdout-class) stderr()?}) → R
:   Runs `body` in a fresh [Zone](../dart-async/zone-class) using the
    provided overrides.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides-class.html>
:::
