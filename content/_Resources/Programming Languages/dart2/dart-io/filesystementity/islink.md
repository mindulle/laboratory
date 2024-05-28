[dart:io](../../dart-io/dart-io-library){._links-link}

isLink method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
isLink(

1.  [String](../../dart-core/string-class) path

)
:::

Whether `path` refers to a link.

Checks whether `type(path, followLinks: false)` returns
[FileSystemEntityType.link](../filesystementitytype/link-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<bool> isLink(String path) => _isLinkRaw(_toUtf8Array(path));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/isLink.html>
:::
