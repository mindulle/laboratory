[dart:collection](../../dart-collection/dart-collection-library){._links-link}

firstKeyAfter method
====================

::: {.section .multi-line-signature}
K? firstKeyAfter(

1.  K key

)
:::

Get the first key in the map that is strictly larger than `key`. Returns
`null` if no key was not found.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
K? firstKeyAfter(K key) {
  if (key == null) throw ArgumentError(key);
  if (_root == null) return null;
  int comp = _splay(key);
  if (comp > 0) return _root!.key;
  _SplayTreeMapNode<K, V>? node = _root!._right;
  if (node == null) return null;
  var nodeLeft = node._left;
  while (nodeLeft != null) {
    node = nodeLeft;
    nodeLeft = node._left;
  }
  return node!.key;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/firstKeyAfter.html>
:::
