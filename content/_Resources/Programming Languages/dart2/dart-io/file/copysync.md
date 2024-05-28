[dart:io](../../dart-io/dart-io-library){._links-link}

copySync method
===============

::: {.section .multi-line-signature}
[File](../file-class) copySync(

1.  [String](../../dart-core/string-class) newPath

)
:::

Synchronously copies this file.

If `newPath` is a relative path, it is resolved against the current
working directory ([Directory.current](../directory/current)).

Returns a [File](../file-class) for the copied file.

If `newPath` identifies an existing file, that file is removed first. If
`newPath` identifies an existing directory the operation fails and an
exception is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
File copySync(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/copySync.html>
:::
