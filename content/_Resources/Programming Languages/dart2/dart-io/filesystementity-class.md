[dart:io](../dart-io/dart-io-library){._links-link}

FileSystemEntity class
======================

The common superclass of [File](file-class),
[Directory](directory-class), and [Link](link-class).

[FileSystemEntity](filesystementity-class) objects are returned from
directory listing operations. To determine whether a
[FileSystemEntity](filesystementity-class) is a [File](file-class), a
[Directory](directory-class), or a [Link](link-class) perform a type
check:

``` {.language-dart data-language="dart"}
if (entity is File) (entity as File).readAsStringSync();
```

You can also use the [type](filesystementity/type) or
[typeSync](filesystementity/typesync) methods to determine the type of a
file system object.

Most methods in this class exist both in synchronous and asynchronous
versions, for example, [exists](filesystementity/exists) and
[existsSync](filesystementity/existssync). Unless you have a specific
reason for using the synchronous version of a method, prefer the
asynchronous version to avoid blocking your program.

Here\'s the exists method in action:

``` {.language-dart data-language="dart"}
var isThere = await entity.exists();
print(isThere ? 'exists' : 'non-existent');
```

Other resources
---------------

-   The [Files and
    directories](https://dart.dev/guides/libraries/library-tour#files-and-directories)
    section of the library tour.

-   [Write Command-Line
    Apps](https://dart.dev/tutorials/server/cmdline), a tutorial about
    writing command-line apps, includes information about files and
    directories.

Implementers

:   -   [Directory](directory-class)
    -   [File](file-class)
    -   [Link](link-class)

Constructors
------------

[FileSystemEntity](filesystementity/filesystementity)()

Properties {#instance-properties}
----------

[absolute](filesystementity/absolute) →
[FileSystemEntity](filesystementity-class)

::: {.features}
read-only
:::

A [FileSystemEntity](filesystementity-class) whose path is the absolute
path of [path](filesystementity/path).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isAbsolute](filesystementity/isabsolute) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether this object\'s path is absolute.

[parent](filesystementity/parent) → [Directory](directory-class)

::: {.features}
read-only
:::

The parent directory of this entity.

[path](filesystementity/path) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[uri](filesystementity/uri) → [Uri](../dart-core/uri-class)

::: {.features}
read-only
:::

A [Uri](../dart-core/uri-class) representing the file system entity\'s
location.

Methods {#instance-methods}
-------

[delete](filesystementity/delete)({[bool](../dart-core/bool-class)
recursive = false}) →
[Future](../dart-async/future-class)\<[FileSystemEntity](filesystementity-class)\>

Deletes this `FileSystemEntity`.

[deleteSync](filesystementity/deletesync)({[bool](../dart-core/bool-class)
recursive = false}) → void

Synchronously deletes this [FileSystemEntity](filesystementity-class).

[exists](filesystementity/exists)() →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

Checks whether the file system entity with this path exists.

[existsSync](filesystementity/existssync)() →
[bool](../dart-core/bool-class)

Synchronously checks whether the file system entity with this path
exists.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[rename](filesystementity/rename)([String](../dart-core/string-class)
newPath) →
[Future](../dart-async/future-class)\<[FileSystemEntity](filesystementity-class)\>

Renames this file system entity.

[renameSync](filesystementity/renamesync)([String](../dart-core/string-class)
newPath) → [FileSystemEntity](filesystementity-class)

Synchronously renames this file system entity.

[resolveSymbolicLinks](filesystementity/resolvesymboliclinks)() →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

Resolves the path of a file system object relative to the current
working directory.

[resolveSymbolicLinksSync](filesystementity/resolvesymboliclinkssync)()
→ [String](../dart-core/string-class)

Resolves the path of a file system object relative to the current
working directory.

[stat](filesystementity/stat)() →
[Future](../dart-async/future-class)\<[FileStat](filestat-class)\>

Calls the operating system\'s `stat()` function on
[path](filesystementity/path).

[statSync](filesystementity/statsync)() → [FileStat](filestat-class)

Synchronously calls the operating system\'s `stat()` function on
[path](filesystementity/path).

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[watch](filesystementity/watch)({[int](../dart-core/int-class) events =
FileSystemEvent.all, [bool](../dart-core/bool-class) recursive = false})
→
[Stream](../dart-async/stream-class)\<[FileSystemEvent](filesystemevent-class)\>

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

Static Properties
-----------------

[isWatchSupported](filesystementity/iswatchsupported) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Test if [watch](filesystementity/watch) is supported on the current
system.

Static Methods
--------------

[identical](filesystementity/identical)([String](../dart-core/string-class) path1, [String](../dart-core/string-class) path2) → [Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>
:   Checks whether two paths refer to the same object in the file
    system.

[identicalSync](filesystementity/identicalsync)([String](../dart-core/string-class) path1, [String](../dart-core/string-class) path2) → [bool](../dart-core/bool-class)
:   Synchronously checks whether two paths refer to the same object in
    the file system.

[isDirectory](filesystementity/isdirectory)([String](../dart-core/string-class) path) → [Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>
:   Whether `path` refers to a directory.

[isDirectorySync](filesystementity/isdirectorysync)([String](../dart-core/string-class) path) → [bool](../dart-core/bool-class)
:   Synchronously checks whether `path` refers to a directory.

[isFile](filesystementity/isfile)([String](../dart-core/string-class) path) → [Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>
:   Whether `path` refers to a file.

[isFileSync](filesystementity/isfilesync)([String](../dart-core/string-class) path) → [bool](../dart-core/bool-class)
:   Synchronously checks whether `path` refers to a file.

[isLink](filesystementity/islink)([String](../dart-core/string-class) path) → [Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>
:   Whether `path` refers to a link.

[isLinkSync](filesystementity/islinksync)([String](../dart-core/string-class) path) → [bool](../dart-core/bool-class)
:   Synchronously checks whether `path` refers to a link.

[parentOf](filesystementity/parentof)([String](../dart-core/string-class) path) → [String](../dart-core/string-class)
:   The parent path of a path.

[type](filesystementity/type)([String](../dart-core/string-class) path, {[bool](../dart-core/bool-class) followLinks = true}) → [Future](../dart-async/future-class)\<[FileSystemEntityType](filesystementitytype-class)\>
:   Finds the type of file system object that a path points to.

[typeSync](filesystementity/typesync)([String](../dart-core/string-class) path, {[bool](../dart-core/bool-class) followLinks = true}) → [FileSystemEntityType](filesystementitytype-class)
:   Synchronously finds the type of file system object that a path
    points to.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity-class.html>
:::
