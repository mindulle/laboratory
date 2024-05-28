[dart:collection](../../dart-collection/dart-collection-library){._links-link}

updateAll method
================

::: {.section .multi-line-signature}
void updateAll(

1.  V update(
    1.  K key,
    2.  V value

    )

)

::: {.features}
override
:::
:::

Updates all values.

Iterates over all entries in the map and updates them with the result of
invoking `update`.

``` {.language-dart data-language="dart"}
final terrestrial = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Earth'};
terrestrial.updateAll((key, value) => value.toUpperCase());
print(terrestrial); // {1: MERCURY, 2: VENUS, 3: EARTH}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void updateAll(V update(K key, V value)) {
  _map.updateAll(update);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapView/updateAll.html>
:::
