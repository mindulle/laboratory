[dart:io](../../dart-io/dart-io-library){._links-link}

destination property
====================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class)? destination

::: {.features}
final
:::
:::

The destination path of the file being moved.

The destination is `null` if the underlying implementation is unable to
identify the destination of the moved file.

The source path is available as [path](../filesystemevent/path).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final String? destination;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemMoveEvent/destination.html>
:::
