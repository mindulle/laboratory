[dart:core](../../dart-core/dart-core-library){._links-link}

Map\<K, V\>.identity constructor
================================

::: {.section .multi-line-signature}
Map\<K, V\>.identity()
:::

Creates an identity map with the default implementation,
[LinkedHashMap](../../dart-collection/linkedhashmap-class).

An identity map uses [identical](../identical) for equality and
[identityHashCode](../identityhashcode) for hash codes of keys instead
of the intrinsic [Object.==](../object/operator_equals) and
[Object.hashCode](../object/hashcode) of the keys.

The map iterates in key insertion order.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Map.identity() = LinkedHashMap<K, V>.identity;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/Map.identity.html>
:::
