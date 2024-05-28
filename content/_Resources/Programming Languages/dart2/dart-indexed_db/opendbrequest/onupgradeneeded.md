[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

onUpgradeNeeded property
========================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[VersionChangeEvent](../versionchangeevent-class)\>
onUpgradeNeeded
:::

Stream of `upgradeneeded` events handled by this
[OpenDBRequest](../opendbrequest-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<VersionChangeEvent> get onUpgradeNeeded =>
    upgradeNeededEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/OpenDBRequest/onUpgradeNeeded.html>
:::
