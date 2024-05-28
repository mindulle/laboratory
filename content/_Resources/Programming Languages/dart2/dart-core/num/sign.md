[dart:core](../../dart-core/dart-core-library){._links-link}

sign property
=============

::: {#getter .section .multi-line-signature}
[num](../num-class) sign
:::

Negative one, zero or positive one depending on the sign and numerical
value of this number.

The value minus one if this number is less than zero, plus one if this
number is greater than zero, and zero if this number is equal to zero.

Returns NaN if this number is a [double](../double-class) NaN value.

Returns a number of the same type as this number. For doubles,
`(-0.0).sign` is `-0.0`.

The result satisfies:

``` {.language-dart data-language="dart"}
n == n.sign * n.abs()
```

for all numbers `n` (except NaN, because NaN isn\'t `==` to itself).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
num get sign;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/sign.html>
:::
