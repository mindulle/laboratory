[dart:collection](../../dart-collection/dart-collection-library){._links-link}

lastKeyBefore method
====================

::: {.section .multi-line-signature}
K? lastKeyBefore(

1.  K key

)
:::

The last key in the map that is strictly smaller than `key`.

Returns `null` if no key was not found.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
K? lastKeyBefore(K key) {
  if (key == null) throw ArgumentError(key);
  if (_root == null) return null;
  int comp = _splay(key);
  if (comp < 0) return _root!.key;
  _SplayTreeMapNode<K, V>? node = _root!._left;
  if (node == null) return null;
  var nodeRight = node._right;
  while (nodeRight != null) {
    node = nodeRight;
    nodeRight = node._right;
  }
  return node!.key;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/lastKeyBefore.html>
:::
