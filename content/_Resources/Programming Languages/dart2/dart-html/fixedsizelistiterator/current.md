[dart:html](../../dart-html/dart-html-library){._links-link}

current property
================

::: {#getter .section .multi-line-signature}
T current

::: {.features}
override
:::
:::

The current element.

If the iterator has not yet been moved to the first element
([moveNext](movenext) has not been called yet), or if the iterator has
been moved past the last element of the
[Iterable](../../dart-core/iterable-class) ([moveNext](movenext) has
returned false), then [current](current) is unspecified. An
[Iterator](../../dart-core/iterator-class) may either throw or return an
iterator specific default value in that case.

The `current` getter should keep its value until the next call to
[moveNext](movenext), even if an underlying collection changes. After a
successful call to `moveNext`, the user doesn\'t need to cache the
current value, but can keep reading it from the iterator.

``` {.language-dart data-language="dart"}
final colors = ['blue', 'yellow', 'red'];
var colorsIterator = colors.iterator;
while (colorsIterator.moveNext()) {
  print(colorsIterator.current);
}
```

The output of the example is:

``` {.language-dart data-language="dart"}
blue
yellow
red
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
T get current => _current as T;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FixedSizeListIterator/current.html>
:::
