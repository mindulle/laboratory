[dart:io](../../dart-io/dart-io-library){._links-link}

createFile method
=================

::: {.section .multi-line-signature}
[File](../file-class) createFile(

1.  [String](../../dart-core/string-class) path

)
:::

Creates a new [File](../file-class) object for the given `path`.

When this override is installed, this function overrides the behavior of
`new File()` and `new File.fromUri()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
File createFile(String path) => new _File(path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/createFile.html>
:::
