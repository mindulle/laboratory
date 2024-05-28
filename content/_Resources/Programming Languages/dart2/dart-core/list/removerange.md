[dart:core](../../dart-core/dart-core-library){._links-link}

removeRange method
==================

::: {.section .multi-line-signature}
void removeRange(

1.  [int](../int-class) start,
2.  [int](../int-class) end

)
:::

Removes a range of elements from the list.

Removes the elements with positions greater than or equal to `start` and
less than `end`, from the list. This reduces the list\'s length by
`end - start`.

The provided range, given by `start` and `end`, must be valid. A range
from `start` to `end` is valid if 0 ≤ `start` ≤ `end` ≤
[length](length). An empty range (with `end == start`) is valid.

The list must be growable.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4, 5];
numbers.removeRange(1, 4);
print(numbers); // [1, 5]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeRange(int start, int end);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/removeRange.html>
:::
