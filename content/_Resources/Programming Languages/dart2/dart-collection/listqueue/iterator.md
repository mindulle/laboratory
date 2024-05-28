[dart:collection](../../dart-collection/dart-collection-library){._links-link}

iterator property
=================

::: {#getter .section .multi-line-signature}
[Iterator](../../dart-core/iterator-class)\<E\> iterator
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

Iterable classes may specify the iteration order of their elements (for
example [List](../../dart-core/list-class) always iterate in index
order), or they may leave it unspecified (for example a hash-based
[Set](../../dart-core/set-class) may iterate in any order).

Each time `iterator` is read, it returns a new iterator, which can be
used to iterate through all the elements again. The iterators of the
same iterable can be stepped through independently, but should return
the same elements in the same order, as long as the underlying
collection isn\'t changed.

Modifying the collection may cause new iterators to produce different
elements, and may change the order of existing elements. A
[List](../../dart-core/list-class) specifies its iteration order
precisely, so modifying the list changes the iteration order
predictably. A hash-based [Set](../../dart-core/set-class) may change
its iteration order completely when adding a new element to the set.

Modifying the underlying collection after creating the new iterator may
cause an error the next time
[Iterator.moveNext](../../dart-core/iterator/movenext) is called on that
iterator. Any *modifiable* iterable class should specify which
operations will break iteration.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterator<E> get iterator => _ListQueueIterator<E>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/iterator.html>
:::
