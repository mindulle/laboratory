[dart:io](../../dart-io/dart-io-library){._links-link}

unlock method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RandomAccessFile](../randomaccessfile-class)\>
unlock(

1.  \[[int](../../dart-core/int-class) start = 0,
2.  [int](../../dart-core/int-class) end = -1\]

)
:::

Unlocks the file or part of the file.

Unlocks the byte range from `start` to `end` of the file, with the byte
at position `end` not included. If no arguments are specified, the full
file is unlocked, If only `start` is specified the file is unlocked from
byte position `start` to the end of the file.

*NOTE* file locking does have slight differences in behavior across
platforms:

See [lock](lock) for more details.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RandomAccessFile> unlock([int start = 0, int end = -1]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/unlock.html>
:::
