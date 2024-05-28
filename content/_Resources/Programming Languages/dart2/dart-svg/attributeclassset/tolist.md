[dart:svg](../../dart-svg/dart-svg-library){._links-link}

toList method
=============

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
toList(

1.  {[bool](../../dart-core/bool-class) growable = true}

)

::: {.features}
inherited
:::
:::

Creates a [List](../../dart-core/list-class) containing the elements of
this [Iterable](../../dart-core/iterable-class).

The elements are in iteration order. The list is fixed-length if
`growable` is false.

Example:

``` {.language-dart data-language="dart"}
final planets = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Mars'};
final keysList = planets.keys.toList(growable: false); // [1, 2, 3]
final valuesList =
    planets.values.toList(growable: false); // [Mercury, Venus, Mars]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<String> toList({bool growable: true}) =>
    readClasses().toList(growable: growable);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/toList.html>
:::
