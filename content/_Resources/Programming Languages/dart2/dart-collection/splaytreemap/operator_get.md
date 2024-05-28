[dart:collection](../../dart-collection/dart-collection-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
V? operator \[\](

1.  [Object](../../dart-core/object-class)? key

)

::: {.features}
override
:::
:::

The value for the given `key`, or `null` if `key` is not in the map.

Some maps allow `null` as a value. For those maps, a lookup using this
operator cannot distinguish between a key not being in the map, and the
key being there with a `null` value. Methods like
[containsKey](containskey) or [putIfAbsent](putifabsent) can be used if
the distinction is important.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
V? operator [](Object? key) {
  if (!_validKey(key)) return null;
  if (_root != null) {
    int comp = _splay(key as dynamic);
    if (comp == 0) {
      return _root!.value;
    }
  }
  return null;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/operator_get.html>
:::
