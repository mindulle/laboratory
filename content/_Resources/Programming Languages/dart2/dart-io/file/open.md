[dart:io](../../dart-io/dart-io-library){._links-link}

open method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RandomAccessFile](../randomaccessfile-class)\>
open(

1.  {[FileMode](../filemode-class) mode = FileMode.read}

)
:::

Opens the file for random access operations.

Returns a `Future<RandomAccessFile>` that completes with the opened
random access file. `RandomAccessFile`s must be closed using the
[RandomAccessFile.close](../randomaccessfile/close) method.

Files can be opened in three modes:

-   [FileMode.read](../filemode/read-constant): open the file for
    reading.

-   [FileMode.write](../filemode/write-constant): open the file for both
    reading and writing and truncate the file to length zero. If the
    file does not exist the file is created.

-   [FileMode.append](../filemode/append-constant): same as
    [FileMode.write](../filemode/write-constant) except that the file is
    not truncated.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RandomAccessFile> open({FileMode mode = FileMode.read});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/open.html>
:::
