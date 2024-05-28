[dart:collection](../../dart-collection/dart-collection-library){._links-link}

getRange method
===============

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<E\> getRange(

1.  [int](../../dart-core/int-class) start,
2.  [int](../../dart-core/int-class) end

)

::: {.features}
override
:::
:::

Creates an [Iterable](../../dart-core/iterable-class) that iterates over
a range of elements.

The returned iterable iterates over the elements of this list with
positions greater than or equal to `start` and less than `end`.

The provided range, `start` and `end`, must be valid at the time of the
call. A range from `start` to `end` is valid if 0 ≤ `start` ≤ `end` ≤
[length](../../dart-core/list/length). An empty range (with
`end == start`) is valid.

The returned [Iterable](../../dart-core/iterable-class) behaves like
`skip(start).take(end - start)`. That is, it does *not* break if this
list changes size, it just ends early if it reaches the end of the list
early (if `end`, or even `start`, becomes greater than
[length](../../dart-core/list/length)).

``` {.language-dart data-language="dart"}
final colors = <String>['red', 'green', 'blue', 'orange', 'pink'];
final firstRange = colors.getRange(0, 3);
print(firstRange.join(', ')); // red, green, blue

final secondRange = colors.getRange(2, 5);
print(secondRange.join(', ')); // blue, orange, pink
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<E> getRange(int start, int end) {
  RangeError.checkValidRange(start, end, this.length);
  return SubListIterable<E>(this, start, end);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/getRange.html>
:::
