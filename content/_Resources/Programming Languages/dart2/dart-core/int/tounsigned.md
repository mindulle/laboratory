[dart:core](../../dart-core/dart-core-library){._links-link}

toUnsigned method
=================

::: {.section .multi-line-signature}
[int](../int-class) toUnsigned(

1.  [int](../int-class) width

)
:::

Returns the least significant `width` bits of this integer as a
non-negative number (i.e. unsigned representation). The returned value
has zeros in all bit positions higher than `width`.

``` {.language-dart data-language="dart"}
(-1).toUnsigned(5) == 31   // 11111111  ->  00011111
```

This operation can be used to simulate arithmetic from low level
languages. For example, to increment an 8 bit quantity:

``` {.language-dart data-language="dart"}
q = (q + 1).toUnsigned(8);
```

`q` will count from `0` up to `255` and then wrap around to `0`.

If the input fits in `width` bits without truncation, the result is the
same as the input. The minimum width needed to avoid truncation of `x`
is given by `x.bitLength`, i.e.

``` {.language-dart data-language="dart"}
x == x.toUnsigned(x.bitLength);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int toUnsigned(int width);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/toUnsigned.html>
:::
