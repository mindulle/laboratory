[dart:collection](../../dart-collection/dart-collection-library){._links-link}

single property
===============

::: {#getter .section .multi-line-signature}
E single

::: {.features}
override
:::
:::

Checks that this iterable has only one element, and returns that
element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty or has more than one element.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E get single {
  // Note that this throws correctly if the queue is empty
  // because reading the element of the sentinel throws.
  if (identical(_sentinel._nextLink, _sentinel._previousLink)) {
    return _sentinel._nextLink!.element;
  }
  throw IterableElementError.tooMany();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/single.html>
:::
