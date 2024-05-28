[dart:io](../../dart-io/dart-io-library){._links-link}

isLinkSync method
=================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isLinkSync(

1.  [String](../../dart-core/string-class) path

)
:::

Synchronously checks whether `path` refers to a link.

Checks whether `typeSync(path, followLinks: false)` returns
[FileSystemEntityType.link](../filesystementitytype/link-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool isLinkSync(String path) => _isLinkRawSync(_toUtf8Array(path));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/isLinkSync.html>
:::
