[dart:core](../../dart-core/dart-core-library){._links-link}

DateTime constructor
====================

::: {.section .multi-line-signature}
DateTime(

1.  [int](../int-class) year,
2.  \[[int](../int-class) month = 1,
3.  [int](../int-class) day = 1,
4.  [int](../int-class) hour = 0,
5.  [int](../int-class) minute = 0,
6.  [int](../int-class) second = 0,
7.  [int](../int-class) millisecond = 0,
8.  [int](../int-class) microsecond = 0\]

)
:::

Constructs a [DateTime](../datetime-class) instance specified in the
local time zone.

For example, to create a `DateTime` object representing the 7th of
September 2017, 5:30pm

``` {.language-dart data-language="dart"}
final dentistAppointment = DateTime(2017, 9, 7, 17, 30);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DateTime(int year,
    [int month = 1,
    int day = 1,
    int hour = 0,
    int minute = 0,
    int second = 0,
    int millisecond = 0,
    int microsecond = 0])
    : this._internal(year, month, day, hour, minute, second, millisecond,
          microsecond, false);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/DateTime.html>
:::
