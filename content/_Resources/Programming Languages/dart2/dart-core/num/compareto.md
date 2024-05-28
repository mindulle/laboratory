[dart:core](../../dart-core/dart-core-library){._links-link}

compareTo method
================

::: {.section .multi-line-signature}
[int](../int-class) compareTo(

1.  [num](../num-class) other

)

::: {.features}
override
:::
:::

Compares this to `other`.

Returns a negative number if `this` is less than `other`, zero if they
are equal, and a positive number if `this` is greater than `other`.

The ordering represented by this method is a total ordering of
[num](../num-class) values. All distinct doubles are non-equal, as are
all distinct integers, but integers are equal to doubles if they have
the same numerical value.

For doubles, the `compareTo` operation is different from the partial
ordering given by [operator==](operator_equals),
[operator\<](operator_less) and [operator\>](operator_greater). For
example, IEEE doubles impose that `0.0 == -0.0` and all comparison
operations on NaN return false.

This function imposes a complete ordering for doubles. When using
`compareTo`, the following properties hold:

-   All NaN values are considered equal, and greater than any numeric
    value.
-   -0.0 is less than 0.0 (and the integer 0), but greater than any
    non-zero negative value.
-   Negative infinity is less than all other values and positive
    infinity is greater than all non-NaN values.
-   All other values are compared using their numeric value.

Examples:

``` {.language-dart data-language="dart"}
print(1.compareTo(2)); // => -1
print(2.compareTo(1)); // => 1
print(1.compareTo(1)); // => 0

// The following comparisons yield different results than the
// corresponding comparison operators.
print((-0.0).compareTo(0.0));  // => -1
print(double.nan.compareTo(double.nan));  // => 0
print(double.infinity.compareTo(double.nan)); // => -1

// -0.0, and NaN comparison operators have rules imposed by the IEEE
// standard.
print(-0.0 == 0.0); // => true
print(double.nan == double.nan);  // => false
print(double.infinity < double.nan);  // => false
print(double.nan < double.infinity);  // => false
print(double.nan == double.infinity);  // => false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int compareTo(num other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/compareTo.html>
:::
