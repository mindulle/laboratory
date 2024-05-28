[dart:io](../../dart-io/dart-io-library){._links-link}

path property
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class)? path

::: {.features}
final
:::
:::

The file system path on which the error occurred.

Can be `null` if the exception does not relate directly to a file system
path.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final String? path;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemException/path.html>
:::
