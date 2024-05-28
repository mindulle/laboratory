[dart:core](../../dart-core/dart-core-library){._links-link}

modInverse method
=================

::: {.section .multi-line-signature}
[int](../int-class) modInverse(

1.  [int](../int-class) modulus

)
:::

Returns the modular multiplicative inverse of this integer modulo
`modulus`.

The `modulus` must be positive.

It is an error if no modular inverse exists.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int modInverse(int modulus);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/modInverse.html>
:::
