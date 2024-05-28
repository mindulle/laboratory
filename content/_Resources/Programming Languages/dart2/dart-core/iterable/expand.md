[dart:core](../../dart-core/dart-core-library){._links-link}

expand\<T\> method
==================

::: {.section .multi-line-signature}
[Iterable](../iterable-class)\<T\> expand\<T\>(

1.  [Iterable](../iterable-class)\<T\> toElements(
    1.  E element

    )

)
:::

Expands each element of this [Iterable](../iterable-class) into zero or
more elements.

The resulting Iterable runs through the elements returned by
`toElements` for each element of this, in iteration order.

The returned [Iterable](../iterable-class) is lazy, and calls
`toElements` for each element of this iterable every time the returned
iterable is iterated.

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
Iterable<T> expand<T>(Iterable<T> toElements(E element)) =>
    ExpandIterable<E, T>(this, toElements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/expand.html>
:::
