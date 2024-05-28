[dart:core](../../dart-core/dart-core-library){._links-link}

Set\<E\> constructor
====================

::: {.section .multi-line-signature}
Set\<E\>()
:::

Creates an empty [Set](../set-class).

The created [Set](../set-class) is a plain
[LinkedHashSet](../../dart-collection/linkedhashset-class). As such, it
considers elements that are equal (using [operator
==](../object/operator_equals)) to be indistinguishable, and requires
them to have a compatible [Object.hashCode](../object/hashcode)
implementation.

The set is equivalent to one created by `LinkedHashSet<E>()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Set() = LinkedHashSet<E>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set/Set.html>
:::
