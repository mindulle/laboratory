[dart:io](../../dart-io/dart-io-library){._links-link}

unlockSync method
=================

::: {.section .multi-line-signature}
void unlockSync(

1.  \[[int](../../dart-core/int-class) start = 0,
2.  [int](../../dart-core/int-class) end = -1\]

)
:::

Synchronously unlocks the file or part of the file.

Unlocks the byte range from `start` to `end` of the file, with the byte
at position `end` not included. If no arguments are specified, the full
file is unlocked, If only `start` is specified the file is unlocked from
byte position `start` to the end of the file.

*NOTE* file locking does have slight differences in behavior across
platforms:

See [lockSync](locksync) for more details.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void unlockSync([int start = 0, int end = -1]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/unlockSync.html>
:::
