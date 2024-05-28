[dart:collection](../../dart-collection/dart-collection-library){._links-link}

retainAll method
================

::: {.section .multi-line-signature}
void retainAll(

1.  [Iterable](../../dart-core/iterable-class)\<[Object](../../dart-core/object-class)?\>
    elements

)

::: {.features}
override
:::
:::

Removes all elements of this set that are not elements in `elements`.

Checks for each element of `elements` whether there is an element in
this set that is equal to it (according to `this.contains`), and if so,
the equal element in this set is retained, and elements that are not
equal to any element in `elements` are removed.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
characters.retainAll({'A', 'B', 'X'});
print(characters); // {A, B}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void retainAll(Iterable<Object?> elements) {
  // Build a set with the same sense of equality as this set.
  SplayTreeSet<E> retainSet = SplayTreeSet<E>(_compare, _validKey);
  int modificationCount = _modificationCount;
  for (Object? object in elements) {
    if (modificationCount != _modificationCount) {
      // The iterator should not have side effects.
      throw ConcurrentModificationError(this);
    }
    // Equivalent to this.contains(object).
    if (_validKey(object) && _splay(object as E) == 0) {
      retainSet.add(_root!.key);
    }
  }
  // Take over the elements from the retained set, if it differs.
  if (retainSet._count != _count) {
    _root = retainSet._root;
    _count = retainSet._count;
    _modificationCount++;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/retainAll.html>
:::
