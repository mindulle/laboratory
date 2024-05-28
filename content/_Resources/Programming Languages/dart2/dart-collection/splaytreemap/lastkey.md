[dart:collection](../../dart-collection/dart-collection-library){._links-link}

lastKey method
==============

::: {.section .multi-line-signature}
K? lastKey()
:::

The last key in the map.

Returns `null` if the map is empty.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
K? lastKey() {
  if (_root == null) return null;
  return _last!.key;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/lastKey.html>
:::
