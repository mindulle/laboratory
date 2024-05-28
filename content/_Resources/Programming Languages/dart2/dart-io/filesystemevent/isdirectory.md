[dart:io](../../dart-io/dart-io-library){._links-link}

isDirectory property
====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isDirectory

::: {.features}
final
:::
:::

Is `true` if the event target was a directory.

Note that if the file has been deleted by the time the event has
arrived, this will always be `false` on Windows. In particular, it will
always be `false` for `delete` events.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final bool isDirectory;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEvent/isDirectory.html>
:::
