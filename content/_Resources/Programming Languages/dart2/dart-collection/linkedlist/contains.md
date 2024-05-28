[dart:collection](../../dart-collection/dart-collection-library){._links-link}

contains method
===============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) contains(

1.  [Object](../../dart-core/object-class)? entry

)

::: {.features}
override
:::
:::

Whether `entry` is a [LinkedListEntry](../linkedlistentry-class)
belonging to this list.

The `entry` is considered as belonging to this list if its
[LinkedListEntry.list](../linkedlistentry/list) is this list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool contains(Object? entry) =>
    entry is LinkedListEntry && identical(this, entry.list);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList/contains.html>
:::
