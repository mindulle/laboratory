[dart:collection](../../dart-collection/dart-collection-library){._links-link}

operator \[\]= method
=====================

::: {.section .multi-line-signature}
void operator \[\]=(

1.  K key,
2.  V value

)

::: {.features}
override
:::
:::

Associates the `key` with the given `value`.

If the key was already in the map, its associated value is changed.
Otherwise the key/value pair is added to the map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
operator []=(K key, V value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapMixin/operator_put.html>
:::
