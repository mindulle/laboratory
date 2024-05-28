[dart:core](../../dart-core/dart-core-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../bool-class) operator ==(

1.  [Object](../object-class) other

)

::: {.features}
override
:::
:::

Test whether this value is numerically equal to `other`.

If both operands are [double](../double-class)s, they are equal if they
have the same representation, except that:

-   zero and minus zero (0.0 and -0.0) are considered equal. They both
    have the numerical value zero.
-   NaN is not equal to anything, including NaN. If either operand is
    NaN, the result is always false.

If one operand is a [double](../double-class) and the other is an
[int](../int-class), they are equal if the double has an integer value
(finite with no fractional part) and the numbers have the same numerical
value.

If both operands are integers, they are equal if they have the same
value.

Returns false if `other` is not a [num](../num-class).

Notice that the behavior for NaN is non-reflexive. This means that
equality of double values is not a proper equality relation, as is
otherwise required of `operator==`. Using NaN in, e.g., a
[HashSet](../../dart-collection/hashset-class) will fail to work. The
behavior is the standard IEEE-754 equality of doubles.

If you can avoid NaN values, the remaining doubles do have a proper
equality relation, and can be used safely.

Use [compareTo](compareto) for a comparison that distinguishes zero and
minus zero, and that considers NaN values as equal.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/operator_equals.html>
:::
