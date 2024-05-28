[dart:io](../../dart-io/dart-io-library){._links-link}

createDirectory method
======================

::: {.section .multi-line-signature}
[Directory](../directory-class) createDirectory(

1.  [String](../../dart-core/string-class) path

)
:::

Creates a new [Directory](../directory-class) object for the given
`path`.

When this override is installed, this function overrides the behavior of
`new Directory()` and `new Directory.fromUri()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Directory createDirectory(String path) => new _Directory(path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/createDirectory.html>
:::
