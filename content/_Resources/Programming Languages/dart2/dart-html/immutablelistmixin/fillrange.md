[dart:html](../../dart-html/dart-html-library){._links-link}

fillRange method
================

::: {.section .multi-line-signature}
void fillRange(

1.  [int](../../dart-core/int-class) start,
2.  [int](../../dart-core/int-class) end,
3.  \[E? fillValue\]

)

::: {.features}
override
:::
:::

Overwrites a range of elements with `fillValue`.

Sets the positions greater than or equal to `start` and less than `end`,
to `fillValue`.

The provided range, given by `start` and `end`, must be valid. A range
from `start` to `end` is valid if 0 ≤ `start` ≤ `end` ≤
[length](../../dart-core/list/length). An empty range (with
`end == start`) is valid.

If the element type is not nullable, the `fillValue` must be provided
and must be non-`null`.

Example:

``` {.language-dart data-language="dart"}
final words = List.filled(5, 'old');
print(words); // [old, old, old, old, old]
words.fillRange(1, 3, 'new');
print(words); // [old, new, new, old, old]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void fillRange(int start, int end, [E? fillValue]) {
  throw new UnsupportedError("Cannot modify an immutable List.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImmutableListMixin/fillRange.html>
:::
