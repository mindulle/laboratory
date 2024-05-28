[dart:collection](../../dart-collection/dart-collection-library){._links-link}

last property
=============

::: {#getter .section .multi-line-signature}
E last

::: {.features}
override
:::
:::

Returns the last element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty. Otherwise may iterate through the elements and returns the last
one seen. Some iterables may have more efficient ways to find the last
element (for example a list can directly access the last element,
without iterating through the previous ones).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E get last {
  Iterator<E> it = iterator;
  if (!it.moveNext()) {
    throw IterableElementError.noElement();
  }
  E result;
  do {
    result = it.current;
  } while (it.moveNext());
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/IterableMixin/last.html>
:::
