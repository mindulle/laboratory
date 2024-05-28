[dart:core](../../dart-core/dart-core-library){._links-link}

abs method
==========

::: {.section .multi-line-signature}
[Duration](../duration-class) abs()
:::

Creates a new [Duration](../duration-class) representing the absolute
length of this [Duration](../duration-class).

The returned [Duration](../duration-class) has the same length as this
one, but is always positive where possible.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration abs() => Duration._microseconds(_duration.abs());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/abs.html>
:::
