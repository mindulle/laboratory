[dart:core](../../dart-core/dart-core-library){._links-link}

operator unary- method
======================

::: {.section .multi-line-signature}
[num](../num-class) operator unary-()
:::

The negation of this value.

The negation of a number is a number of the same kind (`int` or
`double`) representing the negation of the numbers numerical value (the
result of subtracting the number from zero), if that value *exists*.

Negating a double gives a number with the same magnitude as the original
value (`number.abs() == (-number).abs()`), and the opposite sign
(`-(number.sign) == (-number).sign`).

Negating an integer, `-number`, is equivalent to subtracting it from
zero, `0 - number`.

(Both properties generally also hold for the other type, but with a few
edge case exceptions).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
num operator -();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/operator_unary_minus.html>
:::
