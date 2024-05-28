[dart:collection](../../dart-collection/dart-collection-library){._links-link}

UnmodifiableListView\<E\> constructor
=====================================

::: {.section .multi-line-signature}
UnmodifiableListView\<E\>(

1.  [Iterable](../../dart-core/iterable-class)\<E\> source

)
:::

Creates an unmodifiable list backed by `source`.

The `source` of the elements may be a [List](../../dart-core/list-class)
or any [Iterable](../../dart-core/iterable-class) with efficient
[Iterable.length](../../dart-core/iterable/length) and
[Iterable.elementAt](../../dart-core/iterable/elementat).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
UnmodifiableListView(Iterable<E> source) : _source = source;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableListView/UnmodifiableListView.html>
:::
