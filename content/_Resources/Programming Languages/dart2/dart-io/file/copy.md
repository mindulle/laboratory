[dart:io](../../dart-io/dart-io-library){._links-link}

copy method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[File](../file-class)\> copy(

1.  [String](../../dart-core/string-class) newPath

)
:::

Copies this file.

If `newPath` is a relative path, it is resolved against the current
working directory ([Directory.current](../directory/current)).

Returns a `Future<File>` that completes with a `File` for the copied
file.

If `newPath` identifies an existing file, that file is removed first. If
`newPath` identifies an existing directory, the operation fails and the
future completes with an exception.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<File> copy(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/copy.html>
:::
