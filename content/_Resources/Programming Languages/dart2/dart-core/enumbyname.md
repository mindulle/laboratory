[dart:core](../dart-core/dart-core-library){._links-link}

EnumByName\<T extends Enum\> extension
======================================

Access enum values by name.

Extensions on a collection of enum values, intended for use on the
`values` list of an enum type, which allows looking up a value by its
name.

Since enum classes are expected to be relatively small, lookup of
[byName](enumbyname/byname) is performed by linearly iterating through
the values and comparing their name to the provided name. If a more
efficient lookup is needed, perhaps because the lookup operation happens
very often, consider building a map instead using
[asNameMap](enumbyname/asnamemap):

``` {.language-dart data-language="dart"}
static myEnumNameMap = MyEnum.values.asNameMap();
```

and then use that for lookups.

on

:   -   [Iterable](iterable-class)\<T\>

Annotations

-   \@Since(\"2.15\")

Methods {#instance-methods}
-------

[asNameMap](enumbyname/asnamemap)() → [Map](map-class)\<[String](string-class), T\>
:   Creates a map from the names of enum values to the values.

[byName](enumbyname/byname)([String](string-class) name) → T
:   Finds the enum value in this list with name `name`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/EnumByName.html>
:::
