[dart:math](../../dart-math/dart-math-library){._links-link}

nextDouble method
=================

::: {.section .multi-line-signature}
[double](../../dart-core/double-class) nextDouble()
:::

Generates a non-negative random floating point value uniformly
distributed in the range from 0.0, inclusive, to 1.0, exclusive.

Example:

``` {.language-dart data-language="dart"}
var doubleValue = Random().nextDouble(); // Value is >= 0.0 and < 1.0.
doubleValue = Random().nextDouble() * 256; // Value is >= 0.0 and < 256.0.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double nextDouble();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Random/nextDouble.html>
:::
