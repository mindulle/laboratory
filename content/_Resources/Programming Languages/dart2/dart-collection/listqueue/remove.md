[dart:collection](../../dart-collection/dart-collection-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) remove(

1.  [Object](../../dart-core/object-class)? value

)

::: {.features}
override
:::
:::

Removes a single instance of `value` from the queue.

Returns `true` if a value was removed, or `false` if the queue contained
no element equal to `value`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool remove(Object? value) {
  for (int i = _head; i != _tail; i = (i + 1) & (_table.length - 1)) {
    E? element = _table[i];
    if (element == value) {
      _remove(i);
      _modificationCount++;
      return true;
    }
  }
  return false;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/remove.html>
:::
