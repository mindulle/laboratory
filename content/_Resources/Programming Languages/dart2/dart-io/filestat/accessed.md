[dart:io](../../dart-io/dart-io-library){._links-link}

accessed property
=================

::: {.section .multi-line-signature}
[DateTime](../../dart-core/datetime-class) accessed

::: {.features}
final
:::
:::

The time of the last access to the data of the file system object.

On Windows platforms, this may have 1 day granularity, and be out of
date by an hour.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final DateTime accessed;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileStat/accessed.html>
:::
