[dart:core](../../dart-core/dart-core-library){._links-link}

runes property
==============

::: {#getter .section .multi-line-signature}
[Runes](../runes-class) runes
:::

An [Iterable](../iterable-class) of Unicode code-points of this string.

If the string contains surrogate pairs, they are combined and returned
as one integer by this iterator. Unmatched surrogate halves are treated
like valid 16-bit code-units.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Runes get runes;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/runes.html>
:::
