[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashSet\<E\>.identity constructor
=================================

::: {.section .multi-line-signature}
HashSet\<E\>.identity()
:::

Creates an unordered identity-based set.

Effectively shorthand for:

``` {.language-dart data-language="dart"}
HashSet<E>(equals: identical, hashCode: identityHashCode)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory HashSet.identity();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashSet/HashSet.identity.html>
:::
