[dart:io](../../dart-io/dart-io-library){._links-link}

writeFrom method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RandomAccessFile](../randomaccessfile-class)\>
writeFrom(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    buffer,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)
:::

Writes from a `buffer` to the file.

Will read the buffer from index `start` to index `end`. The `start` must
be non-negative and no greater than `buffer`.length. If `end` is
omitted, it defaults to `buffer`.length. Otherwise `end` must be no less
than `start` and no greater than `buffer`.length.

Returns a `Future<RandomAccessFile>` that completes with this
`RandomAccessFile` when the write completes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RandomAccessFile> writeFrom(List<int> buffer,
    [int start = 0, int? end]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/writeFrom.html>
:::
