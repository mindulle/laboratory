[dart:io](../../dart-io/dart-io-library){._links-link}

readInto method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[int](../../dart-core/int-class)\>
readInto(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    buffer,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)
:::

Reads bytes into an existing `buffer`.

Reads bytes and writes then into the range of `buffer` from `start` to
`end`. The `start` must be non-negative and no greater than
`buffer`.length. If `end` is omitted, it defaults to `buffer`.length.
Otherwise `end` must be no less than `start` and no greater than
`buffer`.length.

Returns the number of bytes read. This maybe be less than `end - start`
if the file doesn\'t have that many bytes to read.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<int> readInto(List<int> buffer, [int start = 0, int? end]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/readInto.html>
:::
