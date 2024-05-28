[dart:collection](../../dart-collection/dart-collection-library){._links-link}

firstKey method
===============

::: {.section .multi-line-signature}
K? firstKey()
:::

The first key in the map.

Returns `null` if the map is empty.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
K? firstKey() {
  if (_root == null) return null;
  return _first!.key;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/firstKey.html>
:::
