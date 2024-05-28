[dart:core](../../dart-core/dart-core-library){._links-link}

toSigned method
===============

::: {.section .multi-line-signature}
[BigInt](../bigint-class) toSigned(

1.  [int](../int-class) width

)
:::

Returns the least significant `width` bits of this integer, extending
the highest retained bit to the sign. This is the same as truncating the
value to fit in `width` bits using an signed 2-s complement
representation. The returned value has the same bit value in all
positions higher than `width`.

``` {.language-dart data-language="dart"}
var big15 = BigInt.from(15);
var big16 = BigInt.from(16);
var big239 = BigInt.from(239);
                               //     V--sign bit-V
big16.toSigned(5) == -big16;   //  00010000 -> 11110000
big239.toSigned(5) == big15;   //  11101111 -> 00001111
                               //     ^           ^
```

This operation can be used to simulate arithmetic from low level
languages. For example, to increment an 8 bit signed quantity:

``` {.language-dart data-language="dart"}
q = (q + 1).toSigned(8);
```

`q` will count from `0` up to `127`, wrap to `-128` and count back up to
`127`.

If the input value fits in `width` bits without truncation, the result
is the same as the input. The minimum width needed to avoid truncation
of `x` is `x.bitLength + 1`, i.e.

``` {.language-dart data-language="dart"}
x == x.toSigned(x.bitLength + 1);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
BigInt toSigned(int width);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/toSigned.html>
:::
