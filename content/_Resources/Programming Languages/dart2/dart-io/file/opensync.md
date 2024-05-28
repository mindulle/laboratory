[dart:io](../../dart-io/dart-io-library){._links-link}

openSync method
===============

::: {.section .multi-line-signature}
[RandomAccessFile](../randomaccessfile-class) openSync(

1.  {[FileMode](../filemode-class) mode = FileMode.read}

)
:::

Synchronously opens the file for random access operations.

The result is a [RandomAccessFile](../randomaccessfile-class) on which
random access operations can be performed. Opened
[RandomAccessFile](../randomaccessfile-class)s must be closed using the
[RandomAccessFile.close](../randomaccessfile/close) method.

See [open](open) for information on the `mode` argument.

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RandomAccessFile openSync({FileMode mode = FileMode.read});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/openSync.html>
:::
