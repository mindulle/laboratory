[dart:core](../../dart-core/dart-core-library){._links-link}

any method
==========

::: {.section .multi-line-signature}
[bool](../bool-class) any(

1.  [bool](../bool-class) test(
    1.  E element

    )

)
:::

Checks whether any element of this iterable satisfies `test`.

Checks every element in iteration order, and returns `true` if any of
them make `test` return `true`, otherwise returns false.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
var result = numbers.any((element) => element >= 5); // true;
result = numbers.any((element) => element >= 10); // false;
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool any(bool test(E element)) {
  for (E element in this) {
    if (test(element)) return true;
  }
  return false;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/any.html>
:::
