[dart:io](../dart-io/dart-io-library){._links-link}

RandomAccessFile class
======================

Random access to the data in a file.

`RandomAccessFile` objects are obtained by calling the `open` method on
a [File](file-class) object.

A `RandomAccessFile` has both asynchronous and synchronous methods. The
asynchronous methods all return a [Future](../dart-async/future-class)
whereas the synchronous methods will return the result directly, and
block the current isolate until the result is ready.

At most one asynchronous method can be pending on a given
`RandomAccessFile` instance at the time. If another asynchronous method
is called when one is already in progress, a
[FileSystemException](filesystemexception-class) is thrown.

If an asynchronous method is pending, it is also not possible to call
any synchronous methods. This will also throw a
[FileSystemException](filesystemexception-class).

Constructors
------------

[RandomAccessFile](randomaccessfile/randomaccessfile)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[path](randomaccessfile/path) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The path of the file underlying this random access file.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[close](randomaccessfile/close)() →
[Future](../dart-async/future-class)\<void\>

Closes the file.

[closeSync](randomaccessfile/closesync)() → void

Synchronously closes the file.

[flush](randomaccessfile/flush)() →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Flushes the contents of the file to disk.

[flushSync](randomaccessfile/flushsync)() → void

Synchronously flushes the contents of the file to disk.

[length](randomaccessfile/length)() →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

Gets the length of the file.

[lengthSync](randomaccessfile/lengthsync)() →
[int](../dart-core/int-class)

Synchronously gets the length of the file.

[lock](randomaccessfile/lock)(\[[FileLock](filelock-class) mode =
FileLock.exclusive, [int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class) end = -1\]) →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Locks the file or part of the file.

[lockSync](randomaccessfile/locksync)(\[[FileLock](filelock-class) mode
= FileLock.exclusive, [int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class) end = -1\]) → void

Synchronously locks the file or part of the file.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[position](randomaccessfile/position)() →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

Gets the current byte position in the file.

[positionSync](randomaccessfile/positionsync)() →
[int](../dart-core/int-class)

Synchronously gets the current byte position in the file.

[read](randomaccessfile/read)([int](../dart-core/int-class) count) →
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

Reads up to `count` bytes from a file.

[readByte](randomaccessfile/readbyte)() →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

Reads a byte from the file.

[readByteSync](randomaccessfile/readbytesync)() →
[int](../dart-core/int-class)

Synchronously reads a single byte from the file.

[readInto](randomaccessfile/readinto)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffer, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

Reads bytes into an existing `buffer`.

[readIntoSync](randomaccessfile/readintosync)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffer, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) → [int](../dart-core/int-class)

Synchronously reads into an existing `buffer`.

[readSync](randomaccessfile/readsync)([int](../dart-core/int-class)
count) → [Uint8List](../dart-typed_data/uint8list-class)

Synchronously reads up to `count` bytes from a file

[setPosition](randomaccessfile/setposition)([int](../dart-core/int-class)
position) →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Sets the byte position in the file.

[setPositionSync](randomaccessfile/setpositionsync)([int](../dart-core/int-class)
position) → void

Synchronously sets the byte position in the file.

[toString](randomaccessfile/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
:::

Returns a human-readable string for this random access file.

[truncate](randomaccessfile/truncate)([int](../dart-core/int-class)
length) →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Truncates (or extends) the file to `length` bytes.

[truncateSync](randomaccessfile/truncatesync)([int](../dart-core/int-class)
length) → void

Synchronously truncates (or extends) the file to `length` bytes.

[unlock](randomaccessfile/unlock)(\[[int](../dart-core/int-class) start
= 0, [int](../dart-core/int-class) end = -1\]) →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Unlocks the file or part of the file.

[unlockSync](randomaccessfile/unlocksync)(\[[int](../dart-core/int-class)
start = 0, [int](../dart-core/int-class) end = -1\]) → void

Synchronously unlocks the file or part of the file.

[writeByte](randomaccessfile/writebyte)([int](../dart-core/int-class)
value) →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Writes a single byte to the file.

[writeByteSync](randomaccessfile/writebytesync)([int](../dart-core/int-class)
value) → [int](../dart-core/int-class)

Synchronously writes a single byte to the file.

[writeFrom](randomaccessfile/writefrom)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffer, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Writes from a `buffer` to the file.

[writeFromSync](randomaccessfile/writefromsync)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffer, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) → void

Synchronously writes from a `buffer` to the file.

[writeString](randomaccessfile/writestring)([String](../dart-core/string-class)
string, {[Encoding](../dart-convert/encoding-class) encoding = utf8}) →
[Future](../dart-async/future-class)\<[RandomAccessFile](randomaccessfile-class)\>

Writes a string to the file using the given
[Encoding](../dart-convert/encoding-class).

[writeStringSync](randomaccessfile/writestringsync)([String](../dart-core/string-class)
string, {[Encoding](../dart-convert/encoding-class) encoding = utf8}) →
void

Synchronously writes a single string to the file using the given
[Encoding](../dart-convert/encoding-class).

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
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile-class.html>
:::
