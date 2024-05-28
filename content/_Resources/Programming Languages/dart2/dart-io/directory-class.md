[dart:io](../dart-io/dart-io-library){._links-link}

Directory class
===============

A reference to a directory (or *folder*) on the file system.

A [Directory](directory-class) is an object holding a
[path](directory/path) on which operations can be performed. The path to
the directory can be [absolute](directory/absolute) or relative. It
allows access to the [parent](filesystementity/parent) directory, since
it is a [FileSystemEntity](filesystementity-class).

The [Directory](directory-class) also provides static access to the
system\'s temporary file directory, [systemTemp](directory/systemtemp),
and the ability to access and change the [current](directory/current)
directory.

Create a new [Directory](directory-class) to give access the directory
with the specified path:

``` {.language-dart data-language="dart"}
var myDir = Directory('myDir');
```

Most instance methods of [Directory](directory-class) exist in both
synchronous and asynchronous variants, for example,
[create](directory/create) and [createSync](directory/createsync).
Unless you have a specific reason for using the synchronous version of a
method, prefer the asynchronous version to avoid blocking your program.

Create a directory
------------------

The following code sample creates a directory using the
[create](directory/create) method. By setting the `recursive` parameter
to true, you can create the named directory and all its necessary parent
directories, if they do not already exist.

``` {.language-dart data-language="dart"}
import 'dart:io';

void main() async {
  // Creates dir/ and dir/subdir/.
  var directory = await Directory('dir/subdir').create(recursive: true);
  print(directory.path);
}
```

List the entries of a directory
-------------------------------

Use the [list](directory/list) or [listSync](directory/listsync) methods
to get the files and directories contained in a directory. Set
`recursive` to true to recursively list all subdirectories. Set
`followLinks` to true to follow symbolic links. The list method returns
a [Stream](../dart-async/stream-class) of
[FileSystemEntity](filesystementity-class) objects. Listen on the stream
to access each object as it is found:

``` {.language-dart data-language="dart"}
import 'dart:io';

void main() async {
  // Get the system temp directory.
  var systemTempDir = Directory.systemTemp;

  // List directory contents, recursing into sub-directories,
  // but not following symbolic links.
  await for (var entity in
      systemTempDir.list(recursive: true, followLinks: false)) {
    print(entity.path);
  }
}
```

The use of asynchronous methods
-------------------------------

I/O operations can block a program for some period of time while it
waits for the operation to complete. To avoid this, all methods
involving I/O have an asynchronous variant which returns a
[Future](../dart-async/future-class). This future completes when the I/O
operation finishes. While the I/O operation is in progress, the Dart
program is not blocked, and can perform other operations.

For example, the [exists](filesystementity/exists) method, which
determines whether the directory exists, returns a boolean value
asynchronously using a [Future](../dart-async/future-class).

``` {.language-dart data-language="dart"}
import 'dart:io';

void main() async {
  final myDir = Directory('dir');
  var isThere = await myDir.exists();
  print(isThere ? 'exists' : 'non-existent');
}
```

In addition to [exists](filesystementity/exists), the
[stat](filesystementity/stat), [rename](directory/rename), and other
methods are also asynchronous.

Other resources
---------------

-   The [Files and
    directories](https://dart.dev/guides/libraries/library-tour#files-and-directories)
    section of the library tour.

-   [Write Command-Line
    Apps](https://dart.dev/tutorials/server/cmdline), a tutorial about
    writing command-line apps, includes information about files and
    directories.

Implemented types

:   -   [FileSystemEntity](filesystementity-class)

Constructors
------------

[Directory](directory/directory)([String](../dart-core/string-class)
path)

::: {.constructor-modifier .features}
factory
:::

Creates a [Directory](directory-class) object.

[Directory.fromRawPath](directory/directory.fromrawpath)([Uint8List](../dart-typed_data/uint8list-class)
path)

::: {.constructor-modifier .features}
factory
:::

[Directory.fromUri](directory/directory.fromuri)([Uri](../dart-core/uri-class)
uri)

::: {.constructor-modifier .features}
factory
:::

Create a [Directory](directory-class) from a URI.

Properties {#instance-properties}
----------

[absolute](directory/absolute) → [Directory](directory-class)

::: {.features}
read-only, override
:::

A [Directory](directory-class) whose path is the absolute path of
[this](directory-class).

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

[path](directory/path) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

Gets the path of this directory.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[uri](directory/uri) → [Uri](../dart-core/uri-class)

::: {.features}
read-only, override
:::

A [Uri](../dart-core/uri-class) representing the directory\'s location.

Methods {#instance-methods}
-------

[create](directory/create)({[bool](../dart-core/bool-class) recursive =
false}) →
[Future](../dart-async/future-class)\<[Directory](directory-class)\>

Creates the directory if it doesn\'t exist.

[createSync](directory/createsync)({[bool](../dart-core/bool-class)
recursive = false}) → void

Synchronously creates the directory if it doesn\'t exist.

[createTemp](directory/createtemp)(\[[String](../dart-core/string-class)?
prefix\]) →
[Future](../dart-async/future-class)\<[Directory](directory-class)\>

Creates a temporary directory in this directory.

[createTempSync](directory/createtempsync)(\[[String](../dart-core/string-class)?
prefix\]) → [Directory](directory-class)

Synchronously creates a temporary directory in this directory.

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

[list](directory/list)({[bool](../dart-core/bool-class) recursive =
false, [bool](../dart-core/bool-class) followLinks = true}) →
[Stream](../dart-async/stream-class)\<[FileSystemEntity](filesystementity-class)\>

Lists the sub-directories and files of this
[Directory](directory-class).

[listSync](directory/listsync)({[bool](../dart-core/bool-class)
recursive = false, [bool](../dart-core/bool-class) followLinks = true})
→
[List](../dart-core/list-class)\<[FileSystemEntity](filesystementity-class)\>

Lists the sub-directories and files of this
[Directory](directory-class). Optionally recurses into sub-directories.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[rename](directory/rename)([String](../dart-core/string-class) newPath)
→ [Future](../dart-async/future-class)\<[Directory](directory-class)\>

::: {.features}
override
:::

Renames this directory.

[renameSync](directory/renamesync)([String](../dart-core/string-class)
newPath) → [Directory](directory-class)

::: {.features}
override
:::

Synchronously renames this directory.

[resolveSymbolicLinks](directory/resolvesymboliclinks)() →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
override
:::

Resolves the path of a file system object relative to the current
working directory.

[resolveSymbolicLinksSync](directory/resolvesymboliclinkssync)() →
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
[path](directory/path).

[statSync](filesystementity/statsync)() → [FileStat](filestat-class)

::: {.features}
inherited
:::

Synchronously calls the operating system\'s `stat()` function on
[path](directory/path).

[toString](directory/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

Returns a human readable representation of this
[Directory](directory-class).

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

Static Properties
-----------------

[current](directory/current) ↔ [Directory](directory-class)

::: {.features}
read / write
:::

Creates a directory object pointing to the current working directory.

[systemTemp](directory/systemtemp) → [Directory](directory-class)

::: {.features}
read-only
:::

The system temp directory.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory-class.html>
:::
