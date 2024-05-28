[dart:io](../../dart-io/dart-io-library){._links-link}

create method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[File](../file-class)\> create(

1.  {[bool](../../dart-core/bool-class) recursive = false}

)
:::

Creates the file.

Returns a `Future<File>` that completes with the file when it has been
created.

If `recursive` is `false`, the default, the file is created only if all
directories in its path already exist. If `recursive` is `true`, any
non-existing parent paths are created first.

Existing files are left untouched by [create](create). Calling
[create](create) on an existing file might fail if there are restrictive
permissions on the file.

Completes the future with a
[FileSystemException](../filesystemexception-class) if the operation
fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<File> create({bool recursive = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/create.html>
:::
