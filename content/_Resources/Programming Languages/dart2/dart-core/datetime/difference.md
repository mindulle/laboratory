[dart:core](../../dart-core/dart-core-library){._links-link}

difference method
=================

::: {.section .multi-line-signature}
[Duration](../duration-class) difference(

1.  [DateTime](../datetime-class) other

)
:::

Returns a [Duration](../duration-class) with the difference when
subtracting `other` from [this](../datetime-class).

The returned [Duration](../duration-class) will be negative if `other`
occurs after [this](../datetime-class).

``` {.language-dart data-language="dart"}
final berlinWallFell = DateTime.utc(1989, DateTime.november, 9);
final dDay = DateTime.utc(1944, DateTime.june, 6);

final difference = berlinWallFell.difference(dDay);
print(difference.inDays); // 16592
```

The difference is measured in seconds and fractions of seconds. The
difference above counts the number of fractional seconds between
midnight at the beginning of those dates. If the dates above had been in
local time, not UTC, then the difference between two midnights may not
be a multiple of 24 hours due to daylight saving differences.

For example, in Australia, similar code using local time instead of UTC:

``` {.language-dart data-language="dart"}
final berlinWallFell = DateTime(1989, DateTime.november, 9);
final dDay = DateTime(1944, DateTime.june, 6);
final difference = berlinWallFell.difference(dDay);
print(difference.inDays); // 16591
assert(difference.inDays == 16592);
```

will fail because the difference is actually 16591 days and 23 hours,
and [Duration.inDays](../duration/indays) only returns the number of
whole days.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Duration difference(DateTime other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/difference.html>
:::
