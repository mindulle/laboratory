[dart:io](../../dart-io/dart-io-library){._links-link}

uri property
============

::: {#getter .section .multi-line-signature}
[Uri](../../dart-core/uri-class) uri
:::

A [Uri](../../dart-core/uri-class) representing the file system
entity\'s location.

The returned URI\'s scheme is always \"file\" if the entity\'s
[path](path) is absolute, otherwise the scheme will be empty and the URI
relative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri get uri => new Uri.file(path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/uri.html>
:::
