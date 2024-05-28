[dart:core](../../dart-core/dart-core-library){._links-link}

truncate method
===============

::: {.section .multi-line-signature}
[int](../int-class) truncate()
:::

The integer obtained by discarding any fractional digits from `this`.

Rounds fractional values towards zero.

The number must be finite (see [isFinite](isfinite)).

If the value is greater than the highest representable positive integer,
the result is that highest positive integer. If the value is smaller
than the highest representable negative integer, the result is that
highest negative integer.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int truncate();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/truncate.html>
:::
