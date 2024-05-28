[dart:collection](../../dart-collection/dart-collection-library){._links-link}

setRange method
===============

::: {.section .multi-line-signature}
void setRange(

1.  [int](../../dart-core/int-class) start,
2.  [int](../../dart-core/int-class) end,
3.  [Iterable](../../dart-core/iterable-class)\<E\> iterable,
4.  \[[int](../../dart-core/int-class) skipCount = 0\]

)

::: {.features}
override
:::
:::

Writes some elements of `iterable` into a range of this list.

Copies the objects of `iterable`, skipping `skipCount` objects first,
into the range from `start`, inclusive, to `end`, exclusive, of this
list.

``` {.language-dart data-language="dart"}
final list1 = <int>[1, 2, 3, 4];
final list2 = <int>[5, 6, 7, 8, 9];
// Copies the 4th and 5th items in list2 as the 2nd and 3rd items
// of list1.
const skipCount = 3;
list1.setRange(1, 3, list2, skipCount);
print(list1); // [1, 8, 9, 4]
```

The provided range, given by `start` and `end`, must be valid. A range
from `start` to `end` is valid if 0 ≤ `start` ≤ `end` ≤
[length](../../dart-core/list/length). An empty range (with
`end == start`) is valid.

The `iterable` must have enough objects to fill the range from `start`
to `end` after skipping `skipCount` objects.

If `iterable` is this list, the operation correctly copies the elements
originally in the range from `skipCount` to `skipCount + (end - start)`
to the range `start` to `end`, even if the two ranges overlap.

If `iterable` depends on this list in some other way, no guarantees are
made.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setRange(int start, int end, Iterable<E> iterable, [int skipCount = 0]) {
  RangeError.checkValidRange(start, end, this.length);
  int length = end - start;
  if (length == 0) return;
  RangeError.checkNotNegative(skipCount, "skipCount");

  List<E> otherList;
  int otherStart;
  // TODO(floitsch): Make this accept more.
  if (iterable is List<E>) {
    otherList = iterable;
    otherStart = skipCount;
  } else {
    otherList = iterable.skip(skipCount).toList(growable: false);
    otherStart = 0;
  }
  if (otherStart + length > otherList.length) {
    throw IterableElementError.tooFew();
  }
  if (otherStart < start) {
    // Copy backwards to ensure correct copy if [from] is this.
    for (int i = length - 1; i >= 0; i--) {
      this[start + i] = otherList[otherStart + i];
    }
  } else {
    for (int i = 0; i < length; i++) {
      this[start + i] = otherList[otherStart + i];
    }
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/setRange.html>
:::
