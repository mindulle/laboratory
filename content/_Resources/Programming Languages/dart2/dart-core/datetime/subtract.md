[dart:core](../../dart-core/dart-core-library){._links-link}

subtract method
===============

::: {.section .multi-line-signature}
[DateTime](../datetime-class) subtract(

1.  [Duration](../duration-class) duration

)
:::

Returns a new [DateTime](../datetime-class) instance with `duration`
subtracted from [this](../datetime-class).

``` {.language-dart data-language="dart"}
final today = DateTime.now();
final fiftyDaysAgo = today.subtract(const Duration(days: 50));
```

Notice that the duration being subtracted is actually 50 \* 24 \* 60 \*
60 seconds. If the resulting `DateTime` has a different daylight saving
offset than `this`, then the result won\'t have the same time-of-day as
`this`, and may not even hit the calendar date 50 days earlier.

Be careful when working with dates in local time.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external DateTime subtract(Duration duration);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/subtract.html>
:::
