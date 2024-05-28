[dart:io](../../dart-io/dart-io-library){._links-link}

createSync method
=================

::: {.section .multi-line-signature}
void createSync(

1.  {[bool](../../dart-core/bool-class) recursive = false}

)
:::

Synchronously creates the file.

Existing files are left untouched by [createSync](createsync). Calling
[createSync](createsync) on an existing file might fail if there are
restrictive permissions on the file.

If `recursive` is `false`, the default, the file is created only if all
directories in its path already exist. If `recursive` is `true`, all
non-existing parent paths are created first.

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void createSync({bool recursive = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/createSync.html>
:::
