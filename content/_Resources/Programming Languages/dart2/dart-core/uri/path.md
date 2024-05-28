[dart:core](../../dart-core/dart-core-library){._links-link}

path property
=============

::: {#getter .section .multi-line-signature}
[String](../string-class) path
:::

The path component.

The path is the actual substring of the URI representing the path, and
it is encoded where necessary. To get direct access to the decoded path,
use [pathSegments](pathsegments).

The path value is the empty string if there is no path component.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get path;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/path.html>
:::
