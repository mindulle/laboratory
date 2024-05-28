[dart:core](../../dart-core/dart-core-library){._links-link}

compareByIndex\<T extends Enum\> method
=======================================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.15\")

</div>

[int](../int-class) compareByIndex\<T extends Enum\>(

1.  T value1,
2.  T value2

)

::: {.features}
\@Since(\"2.15\")
:::
:::

Compares two enum values by their [index](index).

A generic [Comparator](../comparator) function for enum types which
orders enum values by their [index](index) value, which corresponds to
the source order of the enum element declarations in the `enum`
declaration.

Example:

``` {.language-dart data-language="dart"}
enum Season { spring, summer, autumn, winter }

void main() {
  var relationByIndex =
      Enum.compareByIndex(Season.spring, Season.summer); // < 0
  relationByIndex =
      Enum.compareByIndex(Season.summer, Season.spring); // > 0
  relationByIndex =
      Enum.compareByIndex(Season.spring, Season.winter); // < 0
  relationByIndex =
      Enum.compareByIndex(Season.winter, Season.spring); // > 0
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.15")
static int compareByIndex<T extends Enum>(T value1, T value2) =>
    value1.index - value2.index;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Enum/compareByIndex.html>
:::
