[dart:collection](../../dart-collection/dart-collection-library){._links-link}

first property
==============

::: {#getter .section .multi-line-signature}
E first

::: {.features}
override
:::
:::

Returns the first element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty. Otherwise returns the first element in the iteration order,
equivalent to `this.elementAt(0)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E get first {
  if (isEmpty) {
    throw StateError('No such element');
  }
  return _first!;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList/first.html>
:::
