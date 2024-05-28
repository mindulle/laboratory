[dart:core](../../dart-core/dart-core-library){._links-link}

checkValueInInterval method
===========================

::: {.section .multi-line-signature}
[int](../int-class) checkValueInInterval(

1.  [int](../int-class) value,
2.  [int](../int-class) minValue,
3.  [int](../int-class) maxValue,
4.  \[[String](../string-class)? name,
5.  [String](../string-class)? message\]

)
:::

Check that an integer `value` lies in a specific interval.

Throws if `value` is not in the interval. The interval is from
`minValue` to `maxValue`, both inclusive.

If `name` or `message` are provided, they are used as the parameter name
and message text of the thrown error.

Returns `value` if it is in the interval.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int checkValueInInterval(int value, int minValue, int maxValue,
    [String? name, String? message]) {
  if (value < minValue || value > maxValue) {
    throw RangeError.range(value, minValue, maxValue, name, message);
  }
  return value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError/checkValueInInterval.html>
:::
