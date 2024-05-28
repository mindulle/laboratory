[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addFirst method
===============

::: {.section .multi-line-signature}
void addFirst(

1.  E value

)

::: {.features}
override
:::
:::

Adds `value` at the beginning of the queue.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addFirst(E value) {
  _sentinel._append(value, this);
  _elementCount++;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/addFirst.html>
:::
