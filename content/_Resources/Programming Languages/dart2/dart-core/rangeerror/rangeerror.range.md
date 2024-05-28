[dart:core](../../dart-core/dart-core-library){._links-link}

RangeError.range constructor
============================

::: {.section .multi-line-signature}
RangeError.range(

1.  [num](../num-class) invalidValue,
2.  [int](../int-class)? minValue,
3.  [int](../int-class)? maxValue,
4.  \[[String](../string-class)? name,
5.  [String](../string-class)? message\]

)
:::

Create a new [RangeError](../rangeerror-class) for a value being outside
the valid range.

The allowed range is from `minValue` to `maxValue`, inclusive. If
`minValue` or `maxValue` are `null`, the range is infinite in that
direction.

For a range from 0 to the length of something, end exclusive, use
[RangeError.index](rangeerror.index).

An optional `name` can specify the argument name that has the invalid
value, and the `message` can override the default error description.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
RangeError.range(num invalidValue, int? minValue, int? maxValue,
    [String? name, String? message])
    : start = minValue,
      end = maxValue,
      super.value(invalidValue, name, message ?? "Invalid value");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError/RangeError.range.html>
:::
