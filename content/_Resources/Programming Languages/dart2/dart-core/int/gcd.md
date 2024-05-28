[dart:core](../../dart-core/dart-core-library){._links-link}

gcd method
==========

::: {.section .multi-line-signature}
[int](../int-class) gcd(

1.  [int](../int-class) other

)
:::

Returns the greatest common divisor of this integer and `other`.

If either number is non-zero, the result is the numerically greatest
integer dividing both `this` and `other`.

The greatest common divisor is independent of the order, so `x.gcd(y)`
is always the same as `y.gcd(x)`.

For any integer `x`, `x.gcd(x)` is `x.abs()`.

If both `this` and `other` is zero, the result is also zero.

Example:

``` {.language-dart data-language="dart"}
print(4.gcd(2)); // 2
print(8.gcd(4)); // 4
print(10.gcd(12)); // 2
print(10.gcd(0)); // 10
print((-2).gcd(-3)); // 1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int gcd(int other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/gcd.html>
:::
