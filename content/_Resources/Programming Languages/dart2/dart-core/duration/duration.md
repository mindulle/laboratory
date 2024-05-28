[dart:core](../../dart-core/dart-core-library){._links-link}

Duration constructor
====================

::: {.section .multi-line-signature}
const Duration(

1.  {[int](../int-class) days = 0,
2.  [int](../int-class) hours = 0,
3.  [int](../int-class) minutes = 0,
4.  [int](../int-class) seconds = 0,
5.  [int](../int-class) milliseconds = 0,
6.  [int](../int-class) microseconds = 0}

)
:::

Creates a new [Duration](../duration-class) object whose value is the
sum of all individual parts.

Individual parts can be larger than the number of those parts in the
next larger unit. For example, `hours` can be greater than 23. If this
happens, the value overflows into the next larger unit, so 26 `hours` is
the same as 2 `hours` and one more `days`. Likewise, values can be
negative, in which case they underflow and subtract from the next larger
unit.

If the total number of microseconds cannot be represented as an integer
value, the number of microseconds might be truncated and it might lose
precision.

All arguments are 0 by default.

``` {.language-dart data-language="dart"}
const duration = Duration(days: 1, hours: 8, minutes: 56, seconds: 59,
  milliseconds: 30, microseconds: 10);
print(duration); // 32:56:59.030010
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Duration(
    {int days = 0,
    int hours = 0,
    int minutes = 0,
    int seconds = 0,
    int milliseconds = 0,
    int microseconds = 0})
    : this._microseconds(microseconds +
          microsecondsPerMillisecond * milliseconds +
          microsecondsPerSecond * seconds +
          microsecondsPerMinute * minutes +
          microsecondsPerHour * hours +
          microsecondsPerDay * days);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/Duration.html>
:::
