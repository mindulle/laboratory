[dart:collection](../../dart-collection/dart-collection-library){._links-link}

replaceRange method
===================

::: {.section .multi-line-signature}
void replaceRange(

1.  [int](../../dart-core/int-class) start,
2.  [int](../../dart-core/int-class) end,
3.  [Iterable](../../dart-core/iterable-class)\<E\> newContents

)

::: {.features}
override
:::
:::

Replaces a range of elements with the elements of `replacements`.

Removes the objects in the range from `start` to `end`, then inserts the
elements of `replacements` at `start`.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4, 5];
final replacements = [6, 7];
numbers.replaceRange(1, 4, replacements);
print(numbers); // [1, 6, 7, 5]
```

The provided range, given by `start` and `end`, must be valid. A range
from `start` to `end` is valid if 0 ≤ `start` ≤ `end` ≤
[length](../../dart-core/list/length). An empty range (with
`end == start`) is valid.

The operation `list.replaceRange(start, end, replacements)` is roughly
equivalent to:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4, 5];
numbers.removeRange(1, 4);
final replacements = [6, 7];
numbers.insertAll(1, replacements);
print(numbers); // [1, 6, 7, 5]
```

but may be more efficient.

The list must be growable. This method does not work on fixed-length
lists, even when `replacements` has the same number of elements as the
replaced range. In that case use [setRange](setrange) instead.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void replaceRange(int start, int end, Iterable<E> newContents) {
  RangeError.checkValidRange(start, end, this.length);
  if (start == this.length) {
    addAll(newContents);
    return;
  }
  if (newContents is! EfficientLengthIterable) {
    newContents = newContents.toList();
  }
  int removeLength = end - start;
  int insertLength = newContents.length;
  if (removeLength >= insertLength) {
    int insertEnd = start + insertLength;
    this.setRange(start, insertEnd, newContents);
    if (removeLength > insertLength) {
      _closeGap(insertEnd, end);
    }
  } else if (end == this.length) {
    int i = start;
    for (E element in newContents) {
      if (i < end) {
        this[i] = element;
      } else {
        add(element);
      }
      i++;
    }
  } else {
    int delta = insertLength - removeLength;
    int oldLength = this.length;
    int insertEnd = start + insertLength; // aka. end + delta.
    for (int i = oldLength - delta; i < oldLength; ++i) {
      add(this[i > 0 ? i : 0]);
    }
    if (insertEnd < oldLength) {
      this.setRange(insertEnd, oldLength, this, end);
    }
    this.setRange(start, insertEnd, newContents);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/replaceRange.html>
:::
