[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

onVersionChange property
========================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[VersionChangeEvent](../versionchangeevent-class)\>
onVersionChange
:::

Stream of `versionchange` events handled by this
[Database](../database-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<VersionChangeEvent> get onVersionChange =>
    versionChangeEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Database/onVersionChange.html>
:::
