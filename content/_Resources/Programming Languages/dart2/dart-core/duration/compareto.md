[dart:core](../../dart-core/dart-core-library){._links-link}

compareTo method
================

::: {.section .multi-line-signature}
[int](../int-class) compareTo(

1.  [Duration](../duration-class) other

)

::: {.features}
override
:::
:::

Compares this [Duration](../duration-class) to `other`, returning zero
if the values are equal.

Returns a negative integer if this [Duration](../duration-class) is
shorter than `other`, or a positive integer if it is longer.

A negative [Duration](../duration-class) is always considered shorter
than a positive one.

It is always the case that `duration1.compareTo(duration2) < 0` iff
`(someDate + duration1).compareTo(someDate + duration2) < 0`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int compareTo(Duration other) => _duration.compareTo(other._duration);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/compareTo.html>
:::
