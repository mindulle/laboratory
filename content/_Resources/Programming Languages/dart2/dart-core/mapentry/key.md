[dart:core](../../dart-core/dart-core-library){._links-link}

key property
============

::: {.section .multi-line-signature}
K key

::: {.features}
final
:::
:::

The key of the entry.

``` {.language-dart data-language="dart"}
final map = {'theKey': 'theValue'};
var entry = map.entries.first;
print(entry.key); // theKey
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final K key;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/MapEntry/key.html>
:::
