[dart:html](../../dart-html/dart-html-library){._links-link}

removeRange method
==================

::: {.section .multi-line-signature}
void removeRange(

1.  [int](../../dart-core/int-class) start,
2.  [int](../../dart-core/int-class) end

)

::: {.features}
override
:::
:::

Removes a range of elements from the list.

Removes the elements with positions greater than or equal to `start` and
less than `end`, from the list. This reduces the list\'s length by
`end - start`.

The provided range, given by `start` and `end`, must be valid. A range
from `start` to `end` is valid if 0 ≤ `start` ≤ `end` ≤
[length](../../dart-core/list/length). An empty range (with
`end == start`) is valid.

The list must be growable.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4, 5];
numbers.removeRange(1, 4);
print(numbers); // [1, 5]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeRange(int start, int end) {
  throw new UnsupportedError("Cannot removeRange on immutable List.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImmutableListMixin/removeRange.html>
:::
