[dart:core](../../dart-core/dart-core-library){._links-link}

asNameMap method
================

::: {.section .multi-line-signature}
[Map](../map-class)\<[String](../string-class), T\> asNameMap()
:::

Creates a map from the names of enum values to the values.

The collection that this method is called on is expected to have enums
with distinct names, like the `values` list of an enum class. Only one
value for each name can occur in the created map, so if two or more enum
values have the same name (either being the same value, or being values
of different enum type), at most one of them will be represented in the
returned map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<String, T> asNameMap() =>
    <String, T>{for (var value in this) value._name: value};
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/EnumByName/asNameMap.html>
:::
