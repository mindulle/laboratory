[dart:core](../../dart-core/dart-core-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
[DateTime](../datetime-class) add(

1.  [Duration](../duration-class) duration

)
:::

Returns a new [DateTime](../datetime-class) instance with `duration`
added to [this](../datetime-class).

``` {.language-dart data-language="dart"}
final today = DateTime.now();
final fiftyDaysFromNow = today.add(const Duration(days: 50));
```

Notice that the duration being added is actually 50 \* 24 \* 60 \* 60
seconds. If the resulting `DateTime` has a different daylight saving
offset than `this`, then the result won\'t have the same time-of-day as
`this`, and may not even hit the calendar date 50 days later.

Be careful when working with dates in local time.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external DateTime add(Duration duration);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/add.html>
:::
