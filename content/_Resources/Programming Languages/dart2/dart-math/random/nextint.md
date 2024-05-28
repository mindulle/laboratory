[dart:math](../../dart-math/dart-math-library){._links-link}

nextInt method
==============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) nextInt(

1.  [int](../../dart-core/int-class) max

)
:::

Generates a non-negative random integer uniformly distributed in the
range from 0, inclusive, to `max`, exclusive.

Implementation note: The default implementation supports `max` values
between 1 and (1\<\<32) inclusive.

Example:

``` {.language-dart data-language="dart"}
var intValue = Random().nextInt(10); // Value is >= 0 and < 10.
intValue = Random().nextInt(100) + 50; // Value is >= 50 and < 150.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int nextInt(int max);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Random/nextInt.html>
:::
