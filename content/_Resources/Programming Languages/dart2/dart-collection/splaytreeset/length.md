[dart:collection](../../dart-collection/dart-collection-library){._links-link}

length property
===============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) length

::: {.features}
override
:::
:::

Returns the number of elements in [this](../splaytreeset-class).

Counting all elements may involve iterating through all elements and can
therefore be slow. Some iterables have a more efficient way to find the
number of elements.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get length => _count;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/length.html>
:::
