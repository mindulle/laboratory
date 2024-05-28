[dart:collection](../../dart-collection/dart-collection-library){._links-link}

removeAll method
================

::: {.section .multi-line-signature}
void removeAll(

1.  [Iterable](../../dart-core/iterable-class)\<[Object](../../dart-core/object-class)?\>
    elements

)

::: {.features}
override
:::
:::

Removes each element of `elements` from this set.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
characters.removeAll({'A', 'B', 'X'});
print(characters); // {C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeAll(Iterable<Object?> elements) {
  for (Object? element in elements) remove(element);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/removeAll.html>
:::
