[dart:core](../../dart-core/dart-core-library){._links-link}

compareTo method
================

::: {.section .multi-line-signature}
[int](../int-class) compareTo(

1.  T other

)
:::

Compares this object to another object.

Returns a value like a [Comparator](../comparator) when comparing `this`
to `other`. That is, it returns a negative integer if `this` is ordered
before `other`, a positive integer if `this` is ordered after `other`,
and zero if `this` and `other` are ordered together.

The `other` argument must be a value that is comparable to this object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int compareTo(T other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Comparable/compareTo.html>
:::
