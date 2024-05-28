[dart:core](../dart-core/dart-core-library){._links-link}

Comparator\<T\> typedef
=======================

::: {.section .multi-line-signature}
Comparator\<T\> = [int](int-class) Function(T a, T b)
:::

The signature of a generic comparison function.

A comparison function represents an ordering on a type of objects. A
total ordering on a type means that for two values, either they are
equal or one is greater than the other (and the latter must then be
smaller than the former).

A [Comparator](comparator) function represents such a total ordering by
returning

-   a negative integer if `a` is smaller than `b`,
-   zero if `a` is equal to `b`, and
-   a positive integer if `a` is greater than `b`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef Comparator<T> = int Function(T a, T b);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Comparator.html>
:::
