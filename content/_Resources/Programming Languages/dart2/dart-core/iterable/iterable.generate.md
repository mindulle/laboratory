[dart:core](../../dart-core/dart-core-library){._links-link}

Iterable\<E\>.generate constructor
==================================

::: {.section .multi-line-signature}
Iterable\<E\>.generate(

1.  [int](../int-class) count,
2.  \[E generator(
    1.  [int](../int-class) index

    )?\]

)
:::

Creates an `Iterable` which generates its elements dynamically.

The generated iterable has `count` elements, and the element at index
`n` is computed by calling `generator(n)`. Values are not cached, so
each iteration computes the values again.

If `generator` is omitted, it defaults to an identity function on
integers `(int x) => x`, so it may only be omitted if the type parameter
allows integer values. That is, if `E` is a super-type of
[int](../int-class).

As an `Iterable`, `Iterable.generate(n, generator))` is equivalent to
`const [0, ..., n - 1].map(generator)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Iterable.generate(int count, [E generator(int index)?]) {
  if (count <= 0) return EmptyIterable<E>();
  return _GeneratorIterable<E>(count, generator);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/Iterable.generate.html>
:::
