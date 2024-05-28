[dart:math](../../dart-math/dart-math-library){._links-link}

Random constructor
==================

::: {.section .multi-line-signature}
Random(

1.  \[[int](../../dart-core/int-class)? seed\]

)
:::

Creates a random number generator.

The optional parameter `seed` is used to initialize the internal state
of the generator. The implementation of the random stream can change
between releases of the library.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Random([int? seed]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Random/Random.html>
:::
