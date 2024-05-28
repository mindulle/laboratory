[dart:core](../../dart-core/dart-core-library){._links-link}

compare method
==============

::: {.section .multi-line-signature}
[int](../int-class) compare(

1.  [Comparable](../comparable-class) a,
2.  [Comparable](../comparable-class) b

)
:::

A [Comparator](../comparator) that compares one comparable to another.

It returns the result of `a.compareTo(b)`. The call may fail at run-time
if `a` is not comparable to the type of `b`.

This utility function is used as the default comparator for ordering
collections, for example in the [List](../list-class) sort function.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int compare(Comparable a, Comparable b) => a.compareTo(b);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Comparable/compare.html>
:::
