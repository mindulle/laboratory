[dart:core](../../dart-core/dart-core-library){._links-link}

forEach method
==============

::: {.section .multi-line-signature}
void forEach(

1.  void action(
    1.  K key,
    2.  V value

    )

)
:::

Applies `action` to each key/value pair of the map.

Calling `action` must not add or remove keys from the map.

``` {.language-dart data-language="dart"}
final planetsByMass = <num, String>{0.81: 'Venus', 1: 'Earth',
  0.11: 'Mars', 17.15: 'Neptune'};

planetsByMass.forEach((key, value) {
  print('$key: $value');
  // 0.81: Venus
  // 1: Earth
  // 0.11: Mars
  // 17.15: Neptune
});
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void forEach(void action(K key, V value));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/forEach.html>
:::
