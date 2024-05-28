[dart:html](../../dart-html/dart-html-library){._links-link}

containsValue method
====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) containsValue(

1.  [Object](../../dart-core/object-class)? value

)

::: {.features}
override
:::
:::

Whether this map contains the given `value`.

Returns true if any of the values in the map are equal to `value`
according to the `==` operator.

``` {.language-dart data-language="dart"}
final moonCount = <String, int>{'Mercury': 0, 'Venus': 0, 'Earth': 1,
  'Mars': 2, 'Jupiter': 79, 'Saturn': 82, 'Uranus': 27, 'Neptune': 14 };
final moons3 = moonCount.containsValue(3); // false
final moons82 = moonCount.containsValue(82); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool containsValue(Object? value) => values.any((e) => e == value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Storage/containsValue.html>
:::
