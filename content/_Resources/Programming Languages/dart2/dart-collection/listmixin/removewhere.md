[dart:collection](../../dart-collection/dart-collection-library){._links-link}

removeWhere method
==================

::: {.section .multi-line-signature}
void removeWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  E element

    )

)

::: {.features}
override
:::
:::

Removes all objects from this list that satisfy `test`.

An object `o` satisfies `test` if `test(o)` is true.

``` {.language-dart data-language="dart"}
final numbers = <String>['one', 'two', 'three', 'four'];
numbers.removeWhere((item) => item.length == 3);
print(numbers); // [three, four]
```

The list must be growable.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeWhere(bool test(E element)) {
  _filter(test, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/removeWhere.html>
:::
