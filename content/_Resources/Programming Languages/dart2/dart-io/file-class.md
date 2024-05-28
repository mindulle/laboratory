[dart:io](../dart-io/dart-io-library){._links-link}

File class
==========

A reference to a file on the file system.

A `File` holds a [path](file/path) on which operations can be performed.
You can get the parent directory of the file using
[parent](filesystementity/parent), a property inherited from
[FileSystemEntity](filesystementity-class).

Create a new `File` object with a pathname to access the specified file
on the file system from your program.

``` {.language-dart data-language="dart"}
var myFile = File('file.txt');
```

The `File` class contains methods for manipulating files and their
contents. Using methods in this class, you can open and close files,
read to and write from them, create and delete them, and check for their
existence.

When reading or writing a file, you can use streams (with
[openRead](file/openread)), random access operations (with
[open](file/open)), or convenience methods such as
[readAsString](file/readasstring),

Most methods in this class occur in synchronous and asynchronous pairs,
for example, [readAsString](file/readasstring) and
[readAsStringSync](file/readasstringsync). Unless you have a specific
reason for using the synchronous version of a method, prefer the
asynchronous version to avoid blocking your program.

If path is a link
-----------------

If [path](file/path) is a symbolic link, rather than a file, then the
methods of `File` operate on the ultimate target of the link, except for
[delete](filesystementity/delete) and
[deleteSync](filesystementity/deletesync), which operate on the link.

Read from a file
----------------

The following code sample reads the entire contents from a file as a
string using the asynchronous [readAsString](file/readasstring) method:

``` {.language-dart data-language="dart"}
import 'dart:async';
import 'dart:io';

void main() {
  File('file.txt').readAsString().then((String contents) {
    print(contents);
  });
}
```

A more flexible and useful way to read a file is with a
[Stream](../dart-async/stream-class). Open the file with
[openRead](file/openread), which returns a stream that provides the data
in the file as chunks of bytes. Read the stream to process the file
contents when available. You can use various transformers in succession
to manipulate the file content into the required format, or to prepare
it for output.

You might want to use a stream to read large files, to manipulate the
data with transformers, or for compatibility with another API, such as
[WebSocket](websocket-class)s.

``` {.language-dart data-language="dart"}
import 'dart:io';
import 'dart:convert';
import 'dart:async';

void main() async {
  final file = File('file.txt');
  Stream<String> lines = file.openRead()
    .transform(utf8.decoder)       // Decode bytes to UTF-8.
    .transform(LineSplitter());    // Convert stream to individual lines.
  try {
    await for (var line in lines) {
      print('$line: ${line.length} characters');
    }
    print('File is now closed.');
  } catch (e) {
    print('Error: $e');
  }
}
```

Write to a file
---------------

To write a string to a file, use the [writeAsString](file/writeasstring)
method:

``` {.language-dart data-language="dart"}
import 'dart:io';

void main() async {
  final filename = 'file.txt';
  var file = await File(filename).writeAsString('some content');
  // Do something with the file.
}
```

You can also write to a file using a
[Stream](../dart-async/stream-class). Open the file with
[openWrite](file/openwrite), which returns an [IOSink](iosink-class) to
which you can write data. Be sure to close the sink with the
[IOSink.close](iosink/close) method.

``` {.language-dart data-language="dart"}
import 'dart:io';

void main() {
  var file = File('file.txt');
  var sink = file.openWrite();
  sink.write('FILE ACCESSED ${DateTime.now()}\n');

  // Close the IOSink to free system resources.
  sink.close();
}
```

The use of asynchronous methods
-------------------------------

To avoid unintentional blocking of the program, several methods are
asynchronous and return a [Future](../dart-async/future-class). For
example, the [length](file/length) method, which gets the length of a
file, returns a [Future](../dart-async/future-class). Wait for the
future to get the result when it\'s ready.

``` {.language-dart data-language="dart"}
import 'dart:io';

void main() async {
  final file = File('file.txt');

  var length = await file.length();
  print(length);
}
```

In addition to length, the [exists](filesystementity/exists),
[lastModified](file/lastmodified), [stat](filesystementity/stat), and
other methods, are asynchronous.

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

[File](file/file)([String](../dart-core/string-class) path)

::: {.constructor-modifier .features}
factory
:::

Creates a [File](file-class) object.

[File.fromRawPath](file/file.fromrawpath)([Uint8List](../dart-typed_data/uint8list-class)
rawPath)

::: {.constructor-modifier .features}
factory
:::

Creates a [File](file-class) object from a raw path.

[File.fromUri](file/file.fromuri)([Uri](../dart-core/uri-class) uri)

::: {.constructor-modifier .features}
factory
:::

Create a [File](file-class) object from a URI.

Properties {#instance-properties}
----------

[absolute](file/absolute) → [File](file-class)

::: {.features}
read-only, override
:::

A [File](file-class) with the absolute path of [path](file/path).

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

[path](file/path) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

Get the path of the file.

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

[copy](file/copy)([String](../dart-core/string-class) newPath) →
[Future](../dart-async/future-class)\<[File](file-class)\>

Copies this file.

[copySync](file/copysync)([String](../dart-core/string-class) newPath) →
[File](file-class)

Synchronously copies this file.

[create](file/create)({[bool](../dart-core/bool-class) recursive =
false}) → [Future](../dart-async/future-class)\<[File](file-class)\>

Creates the file.

[createSync](file/createsync)({[bool](../dart-core/bool-class) recursive
= false}) → void

Synchronously creates the file.

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

[lastAccessed](file/lastaccessed)() →
[Future](../dart-async/future-class)\<[DateTime](../dart-core/datetime-class)\>

The last-accessed time of the file.

[lastAccessedSync](file/lastaccessedsync)() →
[DateTime](../dart-core/datetime-class)

The last-accessed time of the file.

[lastModified](file/lastmodified)() →
[Future](../dart-async/future-class)\<[DateTime](../dart-core/datetime-class)\>

Get the last-modified time of the file.

[lastModifiedSync](file/lastmodifiedsync)() →
[DateTime](../dart-core/datetime-class)

Get the last-modified time of the file.

[length](file/length)() →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

The length of the file.

[lengthSync](file/lengthsync)() → [int](../dart-core/int-class)

The length of the file provided synchronously.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[open](file/open)({[FileMode](filemode-class) mode = FileMode.read}) →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Opens the file for random access operations.

[openRead](file/openread)(\[[int](../dart-core/int-class)? start,
[int](../dart-core/int-class)? end\]) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

Creates a new independent [Stream](../dart-async/stream-class) for the
contents of this file.

[openSync](file/opensync)({[FileMode](filemode-class) mode =
FileMode.read}) → [RandomAccessFile](randomaccessfile-class)

Synchronously opens the file for random access operations.

[openWrite](file/openwrite)({[FileMode](filemode-class) mode =
FileMode.write, [Encoding](../dart-convert/encoding-class) encoding =
utf8}) → [IOSink](iosink-class)

Creates a new independent [IOSink](iosink-class) for the file.

[readAsBytes](file/readasbytes)() →
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

Reads the entire file contents as a list of bytes.

[readAsBytesSync](file/readasbytessync)() →
[Uint8List](../dart-typed_data/uint8list-class)

Synchronously reads the entire file contents as a list of bytes.

[readAsLines](file/readaslines)({[Encoding](../dart-convert/encoding-class)
encoding = utf8}) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>\>

Reads the entire file contents as lines of text using the given
[Encoding](../dart-convert/encoding-class).

[readAsLinesSync](file/readaslinessync)({[Encoding](../dart-convert/encoding-class)
encoding = utf8}) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

Synchronously reads the entire file contents as lines of text using the
given [Encoding](../dart-convert/encoding-class).

[readAsString](file/readasstring)({[Encoding](../dart-convert/encoding-class)
encoding = utf8}) →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

Reads the entire file contents as a string using the given
[Encoding](../dart-convert/encoding-class).

[readAsStringSync](file/readasstringsync)({[Encoding](../dart-convert/encoding-class)
encoding = utf8}) → [String](../dart-core/string-class)

Synchronously reads the entire file contents as a string using the given
[Encoding](../dart-convert/encoding-class).

[rename](file/rename)([String](../dart-core/string-class) newPath) →
[Future](../dart-async/future-class)\<[File](file-class)\>

::: {.features}
override
:::

Renames this file.

[renameSync](file/renamesync)([String](../dart-core/string-class)
newPath) → [File](file-class)

::: {.features}
override
:::

Synchronously renames this file.

[resolveSymbolicLinks](filesystementity/resolvesymboliclinks)() →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Resolves the path of a file system object relative to the current
working directory.

[resolveSymbolicLinksSync](filesystementity/resolvesymboliclinkssync)()
→ [String](../dart-core/string-class)

::: {.features}
inherited
:::

Resolves the path of a file system object relative to the current
working directory.

[setLastAccessed](file/setlastaccessed)([DateTime](../dart-core/datetime-class)
time) → [Future](../dart-async/future-class)

Modifies the time the file was last accessed.

[setLastAccessedSync](file/setlastaccessedsync)([DateTime](../dart-core/datetime-class)
time) → void

Synchronously modifies the time the file was last accessed.

[setLastModified](file/setlastmodified)([DateTime](../dart-core/datetime-class)
time) → [Future](../dart-async/future-class)

Modifies the time the file was last modified.

[setLastModifiedSync](file/setlastmodifiedsync)([DateTime](../dart-core/datetime-class)
time) → void

Synchronously modifies the time the file was last modified.

[stat](filesystementity/stat)() →
[Future](../dart-async/future-class)\<[FileStat](filestat-class)\>

::: {.features}
inherited
:::

Calls the operating system\'s `stat()` function on [path](file/path).

[statSync](filesystementity/statsync)() → [FileStat](filestat-class)

::: {.features}
inherited
:::

Synchronously calls the operating system\'s `stat()` function on
[path](file/path).

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

::: {.features}
inherited
:::

Start watching the [FileSystemEntity](filesystementity-class) for
changes.

[writeAsBytes](file/writeasbytes)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
bytes, {[FileMode](filemode-class) mode = FileMode.write,
[bool](../dart-core/bool-class) flush = false}) →
[Future](../dart-async/future-class)\<[File](file-class)\>

Writes a list of bytes to a file.

[writeAsBytesSync](file/writeasbytessync)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
bytes, {[FileMode](filemode-class) mode = FileMode.write,
[bool](../dart-core/bool-class) flush = false}) → void

Synchronously writes a list of bytes to a file.

[writeAsString](file/writeasstring)([String](../dart-core/string-class)
contents, {[FileMode](filemode-class) mode = FileMode.write,
[Encoding](../dart-convert/encoding-class) encoding = utf8,
[bool](../dart-core/bool-class) flush = false}) →
[Future](../dart-async/future-class)\<[File](file-class)\>

Writes a string to a file.

[writeAsStringSync](file/writeasstringsync)([String](../dart-core/string-class)
contents, {[FileMode](filemode-class) mode = FileMode.write,
[Encoding](../dart-convert/encoding-class) encoding = utf8,
[bool](../dart-core/bool-class) flush = false}) → void

Synchronously writes a string to a file.

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
<https://api.dart.dev/stable/2.18.5/dart-io/File-class.html>
:::
