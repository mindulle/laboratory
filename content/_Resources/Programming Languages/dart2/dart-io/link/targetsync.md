[dart:io](../../dart-io/dart-io-library){._links-link}

targetSync method
=================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) targetSync()
:::

Synchronously gets the target of the link.

Returns the path to the target.

If the returned target is a relative path, it is relative to the
directory containing the link.

If the link does not exist, or is not a link, throws a
[FileSystemException](../filesystemexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String targetSync();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/targetSync.html>
:::
