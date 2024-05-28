[dart:io](../../dart-io/dart-io-library){._links-link}

renameSync method
=================

::: {.section .multi-line-signature}
[File](../file-class) renameSync(

1.  [String](../../dart-core/string-class) newPath

)

::: {.features}
override
:::
:::

Synchronously renames this file.

Returns a [File](../file-class) for the renamed file.

If `newPath` is a relative path, it is resolved against the current
working directory ([Directory.current](../directory/current)). This
means that simply changing the name of a file, but keeping it the
original directory, requires creating a new complete path with the new
name at the end. Example:

``` {.language-dart data-language="dart"}
File changeFileNameOnlySync(File file, String newFileName) {
  var path = file.path;
  var lastSeparator = path.lastIndexOf(Platform.pathSeparator);
  var newPath = path.substring(0, lastSeparator + 1) + newFileName;
  return file.renameSync(newPath);
}
```

On some platforms, a rename operation cannot move a file between
different file systems. If that is the case, instead
[copySync](copysync) the file to the new location and then
[deleteSync](../filesystementity/deletesync) the original.

If `newPath` identifies an existing file, that file is removed first. If
`newPath` identifies an existing directory the operation fails and an
exception is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
File renameSync(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/renameSync.html>
:::
