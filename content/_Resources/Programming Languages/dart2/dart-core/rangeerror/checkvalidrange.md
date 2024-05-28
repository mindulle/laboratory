[dart:core](../../dart-core/dart-core-library){._links-link}

checkValidRange method
======================

::: {.section .multi-line-signature}
[int](../int-class) checkValidRange(

1.  [int](../int-class) start,
2.  [int](../int-class)? end,
3.  [int](../int-class) length,
4.  \[[String](../string-class)? startName,
5.  [String](../string-class)? endName,
6.  [String](../string-class)? message\]

)
:::

Check that a range represents a slice of an indexable object.

Throws if the range is not valid for an indexable object with the given
`length`. A range is valid for an indexable object with a given `length`

if `0 <= [start] <= [end] <= [length]`. An `end` of `null` is considered
equivalent to `length`.

The `startName` and `endName` defaults to `"start"` and `"end"`,
respectively.

Returns the actual `end` value, which is `length` if `end` is `null`,
and `end` otherwise.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int checkValidRange(int start, int? end, int length,
    [String? startName, String? endName, String? message]) {
  // Comparing with `0` as receiver produces better dart2js type inference.
  // Ditto `start > end` below.
  if (0 > start || start > length) {
    startName ??= "start";
    throw RangeError.range(start, 0, length, startName, message);
  }
  if (end != null) {
    if (start > end || end > length) {
      endName ??= "end";
      throw RangeError.range(end, start, length, endName, message);
    }
    return end;
  }
  return length;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError/checkValidRange.html>
:::
