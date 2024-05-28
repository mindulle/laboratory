[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

sublist method
==============

::: {.section .multi-line-signature}
[Int32List](../int32list-class) sublist(

1.  [int](../../dart-core/int-class) start,
2.  \[[int](../../dart-core/int-class)? end\]

)

::: {.features}
inherited
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
L sublist(int start, [int? end]) {
  // NNBD: Spurious error at `end`, `checkValidRange` is legacy.
  int endIndex = RangeError.checkValidRange(start, end!, length);
  int sublistLength = endIndex - start;
  L result = _createList(sublistLength);
  result.setRange(0, sublistLength, _list, start);
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableInt32ListView/sublist.html>
:::
