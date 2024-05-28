[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addAll method
=============

::: {.section .multi-line-signature}
void addAll(

1.  [Iterable](../../dart-core/iterable-class)\<E\> elements

)

::: {.features}
override
:::
:::

Adds all `elements` to this set.

Equivalent to adding each element in `elements` using [add](add), but
some collections may be able to optimize it.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B'};
characters.addAll({'A', 'B', 'C'});
print(characters); // {A, B, C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addAll(Iterable<E> elements) {
  for (E element in elements) add(element);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/addAll.html>
:::
