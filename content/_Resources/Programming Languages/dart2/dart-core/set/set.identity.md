[dart:core](../../dart-core/dart-core-library){._links-link}

Set\<E\>.identity constructor
=============================

::: {.section .multi-line-signature}
Set\<E\>.identity()
:::

Creates an empty identity [Set](../set-class).

The created [Set](../set-class) is a
[LinkedHashSet](../../dart-collection/linkedhashset-class) that uses
identity as equality relation.

The set is equivalent to one created by `LinkedHashSet<E>.identity()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Set.identity() = LinkedHashSet<E>.identity;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set/Set.identity.html>
:::
