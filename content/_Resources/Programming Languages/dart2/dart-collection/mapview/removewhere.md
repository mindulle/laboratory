[dart:collection](../../dart-collection/dart-collection-library){._links-link}

removeWhere method
==================

::: {.section .multi-line-signature}
void removeWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  K key,
    2.  V value

    )

)

::: {.features}
override
:::
:::

Removes all entries of this map that satisfy the given `test`.

``` {.language-dart data-language="dart"}
final terrestrial = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Earth'};
terrestrial.removeWhere((key, value) => value.startsWith('E'));
print(terrestrial); // {1: Mercury, 2: Venus}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeWhere(bool test(K key, V value)) {
  _map.removeWhere(test);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapView/removeWhere.html>
:::
