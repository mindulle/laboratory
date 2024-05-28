[dart:collection](../../dart-collection/dart-collection-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  E value

)

::: {.features}
override
:::
:::

Adds `value` at the end of the queue.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(E value) {
  _sentinel._prepend(value, this);
  _elementCount++;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/add.html>
:::
