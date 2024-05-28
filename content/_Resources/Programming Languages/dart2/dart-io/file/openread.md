[dart:io](../../dart-io/dart-io-library){._links-link}

openRead method
===============

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>\>
openRead(

1.  \[[int](../../dart-core/int-class)? start,
2.  [int](../../dart-core/int-class)? end\]

)
:::

Creates a new independent [Stream](../../dart-async/stream-class) for
the contents of this file.

If `start` is present, the file will be read from byte-offset `start`.
Otherwise from the beginning (index 0).

If `end` is present, only bytes up to byte-index `end` will be read.
Otherwise, until end of file.

In order to make sure that system resources are freed, the stream must
be read to completion or the subscription on the stream must be
cancelled.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<List<int>> openRead([int? start, int? end]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/openRead.html>
:::
