[dart:core](../../dart-core/dart-core-library){._links-link}

checkNotNegative method
=======================

::: {.section .multi-line-signature}
[int](../int-class) checkNotNegative(

1.  [int](../int-class) value,
2.  \[[String](../string-class)? name,
3.  [String](../string-class)? message\]

)
:::

Check that an integer value is non-negative.

Throws if the value is negative.

If `name` or `message` are provided, they are used as the parameter name
and message text of the thrown error. If `name` is omitted, it defaults
to `index`.

Returns `value` if it is not negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int checkNotNegative(int value, [String? name, String? message]) {
  if (value < 0) {
    throw RangeError.range(value, 0, null, name ?? "index", message);
  }
  return value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError/checkNotNegative.html>
:::
