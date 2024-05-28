[dart:collection](../../dart-collection/dart-collection-library){._links-link}

expand\<T\> method
==================

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<T\> expand\<T\>(

1.  [Iterable](../../dart-core/iterable-class)\<T\> f(
    1.  E element

    )

)

::: {.features}
override
:::
:::

Expands each element of this [Iterable](../../dart-core/iterable-class)
into zero or more elements.

The resulting Iterable runs through the elements returned by
`toElements` for each element of this, in iteration order.

The returned [Iterable](../../dart-core/iterable-class) is lazy, and
calls `toElements` for each element of this iterable every time the
returned iterable is iterated.

Example:

``` {.language-dart data-language="dart"}
Iterable<int> count(int n) sync* {
  for (var i = 1; i <= n; i++) {
    yield i;
   }
 }

var numbers = [1, 3, 0, 2];
print(numbers.expand(count)); // (1, 1, 2, 3, 1, 2)
```

Equivalent to:

``` {.language-dart data-language="dart"}
Iterable<T> expand<T>(Iterable<T> toElements(E e)) sync* {
  for (var value in this) {
    yield* toElements(value);
  }
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<T> expand<T>(Iterable<T> f(E element)) =>
    ExpandIterable<E, T>(this, f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/expand.html>
:::
