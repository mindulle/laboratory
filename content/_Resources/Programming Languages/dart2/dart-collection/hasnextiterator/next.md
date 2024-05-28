[dart:collection](../../dart-collection/dart-collection-library){._links-link}

next method
===========

::: {.section .multi-line-signature}
E next()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E next() {
  // Call to hasNext is necessary to make sure we are positioned at the first
  // element when we start iterating.
  if (!hasNext) throw StateError("No more elements");
  assert(_state == _HAS_NEXT_AND_NEXT_IN_CURRENT);
  E result = _iterator.current;
  _move();
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HasNextIterator/next.html>
:::
