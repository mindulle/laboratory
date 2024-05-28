[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashMap\<K, V\>.identity constructor
====================================

::: {.section .multi-line-signature}
HashMap\<K, V\>.identity()
:::

Creates an unordered identity-based map.

Keys of this map are considered equal only to the same object, and do
not use [Object.==](../../dart-core/object/operator_equals) at all.

Effectively shorthand for:

``` {.language-dart data-language="dart"}
HashMap<K, V>(equals: identical, hashCode: identityHashCode)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory HashMap.identity();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashMap/HashMap.identity.html>
:::
