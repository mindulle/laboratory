[dart:html](../../dart-html/dart-html-library){._links-link}

elementAt method
================

::: {.section .multi-line-signature}
[File](../file-class) elementAt(

1.  [int](../../dart-core/int-class) index

)

::: {.features}
override
:::
:::

Returns the `index`th element.

The `index` must be non-negative and less than [length](length). Index
zero represents the first element (so `iterable.elementAt(0)` is
equivalent to `iterable.first`).

May iterate through the elements in iteration order, ignoring the first
`index` elements and then returning the next. Some iterables may have a
more efficient way to find the element.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
final elementAt = numbers.elementAt(4); // 6
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
File elementAt(int index) => this[index];
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileList/elementAt.html>
:::
