[dart:collection](../../dart-collection/dart-collection-library){._links-link}

insertAll method
================

::: {.section .multi-line-signature}
void insertAll(

1.  [int](../../dart-core/int-class) index,
2.  [Iterable](../../dart-core/iterable-class)\<E\> iterable

)

::: {.features}
override
:::
:::

Inserts all objects of `iterable` at position `index` in this list.

This increases the length of the list by the length of `iterable` and
shifts all later objects towards the end of the list.

The list must be growable. The `index` value must be non-negative and no
greater than [length](../../dart-core/list/length).

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4];
final insertItems = [10, 11];
numbers.insertAll(2, insertItems);
print(numbers); // [1, 2, 10, 11, 3, 4]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insertAll(int index, Iterable<E> iterable) {
  RangeError.checkValueInInterval(index, 0, length, "index");
  if (index == length) {
    addAll(iterable);
    return;
  }
  if (iterable is! EfficientLengthIterable || identical(iterable, this)) {
    iterable = iterable.toList();
  }
  int insertionLength = iterable.length;
  if (insertionLength == 0) {
    return;
  }
  // There might be errors after the length change, in which case the list
  // will end up being modified but the operation not complete. Unless we
  // always go through a "toList" we can't really avoid that.
  int oldLength = length;
  for (int i = oldLength - insertionLength; i < oldLength; ++i) {
    add(this[i > 0 ? i : 0]);
  }
  if (iterable.length != insertionLength) {
    // If the iterable's length is linked to this list's length somehow,
    // we can't insert one in the other.
    this.length -= insertionLength;
    throw ConcurrentModificationError(iterable);
  }
  int oldCopyStart = index + insertionLength;
  if (oldCopyStart < oldLength) {
    setRange(oldCopyStart, oldLength, this, index);
  }
  setAll(index, iterable);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/insertAll.html>
:::
