[dart:collection](../../dart-collection/dart-collection-library){._links-link}

skip method
===========

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<E\> skip(

1.  [int](../../dart-core/int-class) n

)

::: {.features}
override
:::
:::

Returns an [Iterable](../../dart-core/iterable-class) that provides all
but the first `count` elements.

When the returned iterable is iterated, it starts iterating over `this`,
first skipping past the initial `count` elements. If `this` has fewer
than `count` elements, then the resulting Iterable is empty. After that,
the remaining elements are iterated in the same order as in this
iterable.

Some iterables may be able to find later elements without first
iterating through earlier elements, for example when iterating a
[List](../../dart-core/list-class). Such iterables are allowed to ignore
the initial skipped elements.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
final result = numbers.skip(4); // (6, 7)
final skipAll = numbers.skip(100); // () - no elements.
```

The `count` must not be negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<E> skip(int n) {
  return SkipIterable<E>(this, n);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/skip.html>
:::
