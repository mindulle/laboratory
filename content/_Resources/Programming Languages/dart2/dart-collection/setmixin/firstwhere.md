[dart:collection](../../dart-collection/dart-collection-library){._links-link}

firstWhere method
=================

::: {.section .multi-line-signature}
E firstWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  E value

    ),
2.  {E orElse( )?}

)

::: {.features}
override
:::
:::

Returns the first element that satisfies the given predicate `test`.

Iterates through elements and returns the first to satisfy `test`.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
var result = numbers.firstWhere((element) => element < 5); // 1
result = numbers.firstWhere((element) => element > 5); // 6
result =
    numbers.firstWhere((element) => element > 10, orElse: () => -1); // -1
```

If no element satisfies `test`, the result of invoking the `orElse`
function is returned. If `orElse` is omitted, it defaults to throwing a
[StateError](../../dart-core/stateerror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E firstWhere(bool test(E value), {E Function()? orElse}) {
  for (E element in this) {
    if (test(element)) return element;
  }
  if (orElse != null) return orElse();
  throw IterableElementError.noElement();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/firstWhere.html>
:::
