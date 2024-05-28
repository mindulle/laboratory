[dart:collection](../../dart-collection/dart-collection-library){._links-link}

lastWhere method
================

::: {.section .multi-line-signature}
E lastWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  E value

    ),
2.  {E orElse( )?}

)

::: {.features}
override
:::
:::

Returns the last element that satisfies the given predicate `test`.

An iterable that can access its elements directly may check its elements
in any order (for example a list starts by checking the last element and
then moves towards the start of the list). The default implementation
iterates elements in iteration order, checks `test(element)` for each,
and finally returns that last one that matched.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
var result = numbers.lastWhere((element) => element < 5); // 3
result = numbers.lastWhere((element) => element > 5); // 7
result = numbers.lastWhere((element) => element > 10,
    orElse: () => -1); // -1
```

If no element satisfies `test`, the result of invoking the `orElse`
function is returned. If `orElse` is omitted, it defaults to throwing a
[StateError](../../dart-core/stateerror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E lastWhere(bool test(E value), {E Function()? orElse}) {
  late E result;
  bool foundMatching = false;
  for (E element in this) {
    if (test(element)) {
      result = element;
      foundMatching = true;
    }
  }
  if (foundMatching) return result;
  if (orElse != null) return orElse();
  throw IterableElementError.noElement();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/lastWhere.html>
:::
