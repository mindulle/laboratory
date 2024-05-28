[dart:core](../../dart-core/dart-core-library){._links-link}

compareByName\<T extends Enum\> method
======================================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.15\")

</div>

[int](../int-class) compareByName\<T extends Enum\>(

1.  T value1,
2.  T value2

)

::: {.features}
\@Since(\"2.15\")
:::
:::

Compares enum values by name.

The [EnumName.name](../enumname/name) of an enum value is a string
representing the source name used to declare that enum value.

This [Comparator](../comparator) compares two enum values by comparing
their names, and can be used to sort enum values by their names. The
comparison uses [String.compareTo](../string/compareto), and is
therefore case sensitive.

Example:

``` {.language-dart data-language="dart"}
enum Season { spring, summer, autumn, winter }

void main() {
  var seasons = [...Season.values]..sort(Enum.compareByName);
  print(seasons);
  // [Season.autumn, Season.spring, Season.summer, Season.winter]
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.15")
static int compareByName<T extends Enum>(T value1, T value2) =>
    value1.name.compareTo(value2.name);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Enum/compareByName.html>
:::
