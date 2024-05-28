[dart:math](../dart-math/dart-math-library){._links-link}

pow function
============

::: {.section .multi-line-signature}
[num](../dart-core/num-class) pow(

1.  [num](../dart-core/num-class) x,
2.  [num](../dart-core/num-class) exponent

)
:::

Returns `x` to the power of `exponent`.

If `x` is an [int](../dart-core/int-class) and `exponent` is a
non-negative [int](../dart-core/int-class), the result is an
[int](../dart-core/int-class), otherwise both arguments are converted to
doubles first, and the result is a [double](../dart-core/double-class).

For integers, the power is always equal to the mathematical result of
`x` to the power `exponent`, only limited by the available memory.

For doubles, `pow(x, y)` handles edge cases as follows:

-   if `y` is zero (0.0 or -0.0), the result is always 1.0.
-   if `x` is 1.0, the result is always 1.0.
-   otherwise, if either `x` or `y` is NaN, then the result is NaN.
-   if `x` is negative (but not -0.0) and `y` is a finite non-integer,
    the result is NaN.
-   if `x` is Infinity and `y` is negative, the result is 0.0.
-   if `x` is Infinity and `y` is positive, the result is Infinity.
-   if `x` is 0.0 and `y` is negative, the result is Infinity.
-   if `x` is 0.0 and `y` is positive, the result is 0.0.
-   if `x` is -Infinity or -0.0 and `y` is an odd integer, then the
    result is `-pow(-x ,y)`.
-   if `x` is -Infinity or -0.0 and `y` is not an odd integer, then the
    result is the same as `pow(-x , y)`.
-   if `y` is Infinity and the absolute value of `x` is less than 1, the
    result is 0.0.
-   if `y` is Infinity and `x` is -1, the result is 1.0.
-   if `y` is Infinity and the absolute value of `x` is greater than 1,
    the result is Infinity.
-   if `y` is -Infinity, the result is `1/pow(x, Infinity)`.

This corresponds to the `pow` function defined in the IEEE Standard
754-2008.

Notice that the result may overflow. If integers are represented as
64-bit numbers, an integer result may be truncated, and a double result
may overflow to positive or negative
[double.infinity](../dart-core/double/infinity-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external num pow(num x, num exponent);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/pow.html>
:::
