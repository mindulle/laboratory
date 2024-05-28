[dart:core](../../dart-core/dart-core-library){._links-link}

length property
===============

::: {#getter .section .multi-line-signature}
[int](../int-class) length
:::

Returns the number of elements in [this](../iterable-class).

Counting all elements may involve iterating through all elements and can
therefore be slow. Some iterables have a more efficient way to find the
number of elements.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get length {
  assert(this is! EfficientLengthIterable);
  int count = 0;
  Iterator it = iterator;
  while (it.moveNext()) {
    count++;
  }
  return count;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/length.html>
:::
