[dart:collection](../../dart-collection/dart-collection-library){._links-link}

toSet method
============

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<E\> toSet()

::: {.features}
override
:::
:::

Creates a [Set](../../dart-core/set-class) with the same elements and
behavior as this `Set`.

The returned set behaves the same as this set with regard to adding and
removing elements. It initially contains the same elements. If this set
specifies an ordering of the elements, the returned set will have the
same order.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<E> toSet() => _source.toSet();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableSetView/toSet.html>
:::
