[dart:collection](../../dart-collection/dart-collection-library){._links-link}

hasNext property
================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) hasNext
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get hasNext {
  if (_state == _NOT_MOVED_YET) _move();
  return _state == _HAS_NEXT_AND_NEXT_IN_CURRENT;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HasNextIterator/hasNext.html>
:::
