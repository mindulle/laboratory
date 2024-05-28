[dart:io](../../dart-io/dart-io-library){._links-link}

lock method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RandomAccessFile](../randomaccessfile-class)\>
lock(

1.  \[[FileLock](../filelock-class) mode = FileLock.exclusive,
2.  [int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class) end = -1\]

)
:::

Locks the file or part of the file.

By default an exclusive lock will be obtained, but that can be
overridden by the `mode` argument.

Locks the byte range from `start` to `end` of the file, with the byte at
position `end` not included. If no arguments are specified, the full
file is locked, If only `start` is specified the file is locked from
byte position `start` to the end of the file, no matter how large it
grows. It is possible to specify an explicit value of `end` which is
past the current length of the file.

To obtain an exclusive lock on a file, it must be opened for writing.

If `mode` is [FileLock.exclusive](../filelock/exclusive-constant) or
[FileLock.shared](../filelock/shared-constant), an error is signaled if
the lock cannot be obtained. If `mode` is
[FileLock.blockingExclusive](../filelock/blockingexclusive-constant) or
[FileLock.blockingShared](../filelock/blockingshared-constant), the
returned [Future](../../dart-async/future-class) is resolved only when
the lock has been obtained.

*NOTE* file locking does have slight differences in behavior across
platforms:

On Linux and OS X this uses advisory locks, which have the surprising
semantics that all locks associated with a given file are removed when
*any* file descriptor for that file is closed by the process. Note that
this does not actually lock the file for access. Also note that advisory
locks are on a process level. This means that several isolates in the
same process can obtain an exclusive lock on the same file.

On Windows the regions used for lock and unlock needs to match. If that
is not the case unlocking will result in the OS error \"The segment is
already unlocked\".

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RandomAccessFile> lock(
    [FileLock mode = FileLock.exclusive, int start = 0, int end = -1]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/lock.html>
:::
