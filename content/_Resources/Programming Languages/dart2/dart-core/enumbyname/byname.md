[dart:core](../../dart-core/dart-core-library){._links-link}

byName method
=============

::: {.section .multi-line-signature}
T byName(

1.  [String](../string-class) name

)
:::

Finds the enum value in this list with name `name`.

Goes through this collection looking for an enum with name `name`, as
reported by [EnumName.name](../enumname/name). Returns the first value
with the given name. Such a value must be found.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
T byName(String name) {
  for (var value in this) {
    if (value._name == name) return value;
  }
  throw ArgumentError.value(name, "name", "No enum value with that name");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/EnumByName/byName.html>
:::
