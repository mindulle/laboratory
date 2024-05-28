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

Removes all elements of this set that satisfy `test`.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
characters.removeWhere((element) => element.startsWith('B'));
print(characters); // {A, C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeWhere(bool test(E element)) {
  List<Object?> toRemove = [];
  for (E element in this) {
    if (test(element)) toRemove.add(element);
  }
  removeAll(toRemove);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/removeWhere.html>
:::
