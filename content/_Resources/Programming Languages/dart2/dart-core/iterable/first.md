[dart:core](../../dart-core/dart-core-library){._links-link}

first property
==============

::: {#getter .section .multi-line-signature}
E first
:::

Returns the first element.

Throws a [StateError](../stateerror-class) if `this` is empty. Otherwise
returns the first element in the iteration order, equivalent to
`this.elementAt(0)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E get first {
  Iterator<E> it = iterator;
  if (!it.moveNext()) {
    throw IterableElementError.noElement();
  }
  return it.current;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/first.html>
:::
