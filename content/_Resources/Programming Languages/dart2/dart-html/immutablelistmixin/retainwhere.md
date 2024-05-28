[dart:html](../../dart-html/dart-html-library){._links-link}

retainWhere method
==================

::: {.section .multi-line-signature}
void retainWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  E element

    )

)

::: {.features}
override
:::
:::

Removes all objects from this list that fail to satisfy `test`.

An object `o` satisfies `test` if `test(o)` is true.

``` {.language-dart data-language="dart"}
final numbers = <String>['one', 'two', 'three', 'four'];
numbers.retainWhere((item) => item.length == 3);
print(numbers); // [one, two]
```

The list must be growable.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void retainWhere(bool test(E element)) {
  throw new UnsupportedError("Cannot remove from immutable List.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImmutableListMixin/retainWhere.html>
:::
