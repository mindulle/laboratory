[dart:core](../dart-core/dart-core-library){._links-link}

DateTime class
==============

An instant in time, such as July 20, 1969, 8:18pm GMT.

DateTimes can represent time values that are at a distance of at most
100,000,000 days from epoch (1970-01-01 UTC): -271821-04-20 to
275760-09-13.

Create a `DateTime` object by using one of the constructors or by
parsing a correctly formatted string, which complies with a subset of
ISO 8601. **Note:** hours are specified between 0 and 23, as in a
24-hour clock.

For example:

``` {.language-dart data-language="dart"}
final now = DateTime.now();
final berlinWallFell = DateTime.utc(1989, 11, 9);
final moonLanding = DateTime.parse('1969-07-20 20:18:04Z'); // 8:18pm
```

A `DateTime` object is anchored either in the UTC time zone or in the
local time zone of the current computer when the object is created.

Once created, neither the value nor the time zone of a `DateTime` object
may be changed.

You can use properties to get the individual units of a `DateTime`
object.

``` {.language-dart data-language="dart"}
print(berlinWallFell.year); // 1989
print(berlinWallFell.month); // 11
print(berlinWallFell.day); // 9
print(moonLanding.hour); // 20
print(moonLanding.minute); // 18
```

For convenience and readability, the `DateTime` class provides a
constant for each `day` and `month` name - for example,
[august](datetime/august-constant) and
[friday](datetime/friday-constant). You can use these constants to
improve code readability:

``` {.language-dart data-language="dart"}
final berlinWallFell = DateTime.utc(1989, DateTime.november, 9);
print(DateTime.november); // 11
assert(berlinWallFell.month == DateTime.november);
assert(berlinWallFell.weekday == DateTime.thursday);
```

`Day` and `month` values begin at 1, and the week starts on `Monday`.
That is, the constants [january](datetime/january-constant) and
[monday](datetime/monday-constant) are both 1.

Working with UTC and local time
-------------------------------

A `DateTime` object is in the local time zone unless explicitly created
in the UTC time zone. Use [isUtc](datetime/isutc) to determine whether a
`DateTime` object is based in UTC.

``` {.language-dart data-language="dart"}
final dDay = DateTime.utc(1944, 6, 6);
print(dDay.isUtc); // true

final dDayLocal = DateTime(1944, 6, 6);
print(dDayLocal.isUtc); // false
```

Use the methods [toLocal](datetime/tolocal) and [toUtc](datetime/toutc)
to get the equivalent date/time value specified in the other time zone.

``` {.language-dart data-language="dart"}
final localDay = dDay.toLocal(); // e.g. 1944-06-06 02:00:00.000
print(localDay.isUtc); // false

final utcFromLocal = localDay.toUtc(); // 1944-06-06 00:00:00.000Z
print(utcFromLocal.isUtc); // true
```

Use [timeZoneName](datetime/timezonename) to get an abbreviated name of
the time zone for the `DateTime` object.

``` {.language-dart data-language="dart"}
print(dDay.timeZoneName); // UTC
print(localDay.timeZoneName); // e.g. EET
```

To find the difference between UTC and the time zone of a `DateTime`
object call [timeZoneOffset](datetime/timezoneoffset).

``` {.language-dart data-language="dart"}
print(dDay.timeZoneOffset); // 0:00:00.000000
print(localDay.timeZoneOffset); // e.g. 2:00:00.000000
```

Comparing DateTime objects
--------------------------

The `DateTime` class contains methods for comparing `DateTime`s
chronologically, such as [isAfter](datetime/isafter),
[isBefore](datetime/isbefore), and
[isAtSameMomentAs](datetime/isatsamemomentas).

``` {.language-dart data-language="dart"}
print(berlinWallFell.isAfter(moonLanding)); // true
print(berlinWallFell.isBefore(moonLanding)); // false
print(dDay.isAtSameMomentAs(localDay)); // true
```

Using DateTime with Duration
----------------------------

Use the [add](datetime/add) and [subtract](datetime/subtract) methods
with a [Duration](duration-class) object to create a `DateTime` object
based on another. For example, to find the point in time that is 36
hours after now, you can write:

``` {.language-dart data-language="dart"}
final now = DateTime.now();
final later = now.add(const Duration(hours: 36));
```

To find out how much time is between two `DateTime` objects use
[difference](datetime/difference), which returns a
[Duration](duration-class) object:

``` {.language-dart data-language="dart"}
final difference = berlinWallFell.difference(moonLanding);
print(difference.inDays); // 7416
```

The difference between two dates in different time zones is just the
number of nanoseconds between the two points in time. It doesn\'t take
calendar days into account. That means that the difference between two
midnights in local time may be less than 24 hours times the number of
days between them, if there is a daylight saving change in between. If
the difference above is calculated using Australian local time, the
difference is 7415 days and 23 hours, which is only 7415 whole days as
reported by `inDays`.

Other resources
---------------

-   See [Duration](duration-class) to represent a span of time.
-   See [Stopwatch](stopwatch-class) to measure timespans.
-   The `DateTime` class does not provide internationalization. To
    internationalize your code, use the
    [intl](https://pub.dev/packages/intl) package.

Implemented types

:   -   [Comparable](comparable-class)\<[DateTime](datetime-class)\>

Constructors
------------

[DateTime](datetime/datetime)([int](int-class) year, \[[int](int-class) month = 1, [int](int-class) day = 1, [int](int-class) hour = 0, [int](int-class) minute = 0, [int](int-class) second = 0, [int](int-class) millisecond = 0, [int](int-class) microsecond = 0\])
:   Constructs a [DateTime](datetime-class) instance specified in the
    local time zone.

[DateTime.fromMicrosecondsSinceEpoch](datetime/datetime.frommicrosecondssinceepoch)([int](int-class) microsecondsSinceEpoch, {[bool](bool-class) isUtc = false})
:   Constructs a new [DateTime](datetime-class) instance with the given
    `microsecondsSinceEpoch`.

[DateTime.fromMillisecondsSinceEpoch](datetime/datetime.frommillisecondssinceepoch)([int](int-class) millisecondsSinceEpoch, {[bool](bool-class) isUtc = false})
:   Constructs a new [DateTime](datetime-class) instance with the given
    `millisecondsSinceEpoch`.

[DateTime.now](datetime/datetime.now)()
:   Constructs a [DateTime](datetime-class) instance with current date
    and time in the local time zone.

[DateTime.utc](datetime/datetime.utc)([int](int-class) year, \[[int](int-class) month = 1, [int](int-class) day = 1, [int](int-class) hour = 0, [int](int-class) minute = 0, [int](int-class) second = 0, [int](int-class) millisecond = 0, [int](int-class) microsecond = 0\])
:   Constructs a [DateTime](datetime-class) instance specified in the
    UTC time zone.

Properties {#instance-properties}
----------

[day](datetime/day) → [int](int-class)

::: {.features}
read-only
:::

The day of the month `[1..31]`.

[hashCode](datetime/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

The hash code for this object.

[hour](datetime/hour) → [int](int-class)

::: {.features}
read-only
:::

The hour of the day, expressed as in a 24-hour clock `[0..23]`.

[isUtc](datetime/isutc) → [bool](bool-class)

::: {.features}
final
:::

True if this [DateTime](datetime-class) is set to UTC time.

[microsecond](datetime/microsecond) → [int](int-class)

::: {.features}
read-only
:::

The microsecond `[0...999]`.

[microsecondsSinceEpoch](datetime/microsecondssinceepoch) →
[int](int-class)

::: {.features}
read-only
:::

The number of microseconds since the \"Unix epoch\" 1970-01-01T00:00:00Z
(UTC).

[millisecond](datetime/millisecond) → [int](int-class)

::: {.features}
read-only
:::

The millisecond `[0...999]`.

[millisecondsSinceEpoch](datetime/millisecondssinceepoch) →
[int](int-class)

::: {.features}
read-only
:::

The number of milliseconds since the \"Unix epoch\" 1970-01-01T00:00:00Z
(UTC).

[minute](datetime/minute) → [int](int-class)

::: {.features}
read-only
:::

The minute `[0...59]`.

[month](datetime/month) → [int](int-class)

::: {.features}
read-only
:::

The month `[1..12]`.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[second](datetime/second) → [int](int-class)

::: {.features}
read-only
:::

The second `[0...59]`.

[timeZoneName](datetime/timezonename) → [String](string-class)

::: {.features}
read-only
:::

The time zone name.

[timeZoneOffset](datetime/timezoneoffset) → [Duration](duration-class)

::: {.features}
read-only
:::

The time zone offset, which is the difference between local time and
UTC.

[weekday](datetime/weekday) → [int](int-class)

::: {.features}
read-only
:::

The day of the week
[monday](datetime/monday-constant)..[sunday](datetime/sunday-constant).

[year](datetime/year) → [int](int-class)

::: {.features}
read-only
:::

The year.

Methods {#instance-methods}
-------

[add](datetime/add)([Duration](duration-class) duration) →
[DateTime](datetime-class)

Returns a new [DateTime](datetime-class) instance with `duration` added
to [this](datetime-class).

[compareTo](datetime/compareto)([DateTime](datetime-class) other) →
[int](int-class)

::: {.features}
override
:::

Compares this DateTime object to `other`, returning zero if the values
are equal.

[difference](datetime/difference)([DateTime](datetime-class) other) →
[Duration](duration-class)

Returns a [Duration](duration-class) with the difference when
subtracting `other` from [this](datetime-class).

[isAfter](datetime/isafter)([DateTime](datetime-class) other) →
[bool](bool-class)

Returns true if [this](datetime-class) occurs after `other`.

[isAtSameMomentAs](datetime/isatsamemomentas)([DateTime](datetime-class)
other) → [bool](bool-class)

Returns true if [this](datetime-class) occurs at the same moment as
`other`.

[isBefore](datetime/isbefore)([DateTime](datetime-class) other) →
[bool](bool-class)

Returns true if [this](datetime-class) occurs before `other`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[subtract](datetime/subtract)([Duration](duration-class) duration) →
[DateTime](datetime-class)

Returns a new [DateTime](datetime-class) instance with `duration`
subtracted from [this](datetime-class).

[toIso8601String](datetime/toiso8601string)() → [String](string-class)

Returns an ISO-8601 full-precision extended format representation.

[toLocal](datetime/tolocal)() → [DateTime](datetime-class)

Returns this DateTime value in the local time zone.

[toString](datetime/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns a human-readable string for this instance.

[toUtc](datetime/toutc)() → [DateTime](datetime-class)

Returns this DateTime value in the UTC time zone.

Operators
---------

[operator ==](datetime/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

Returns true if `other` is a [DateTime](datetime-class) at the same
moment and in the same time zone (UTC or local).

Static Methods
--------------

[parse](datetime/parse)([String](string-class) formattedString) → [DateTime](datetime-class)
:   Constructs a new [DateTime](datetime-class) instance based on
    `formattedString`.

[tryParse](datetime/tryparse)([String](string-class) formattedString) → [DateTime](datetime-class)?
:   Constructs a new [DateTime](datetime-class) instance based on
    `formattedString`.

Constants
---------

[april](datetime/april-constant) → const [int](int-class)

:   <div>

    `4`

    </div>

[august](datetime/august-constant) → const [int](int-class)

:   <div>

    `8`

    </div>

[daysPerWeek](datetime/daysperweek-constant) → const [int](int-class)

:   <div>

    `7`

    </div>

[december](datetime/december-constant) → const [int](int-class)

:   <div>

    `12`

    </div>

[february](datetime/february-constant) → const [int](int-class)

:   <div>

    `2`

    </div>

[friday](datetime/friday-constant) → const [int](int-class)

:   <div>

    `5`

    </div>

[january](datetime/january-constant) → const [int](int-class)

:   <div>

    `1`

    </div>

[july](datetime/july-constant) → const [int](int-class)

:   <div>

    `7`

    </div>

[june](datetime/june-constant) → const [int](int-class)

:   <div>

    `6`

    </div>

[march](datetime/march-constant) → const [int](int-class)

:   <div>

    `3`

    </div>

[may](datetime/may-constant) → const [int](int-class)

:   <div>

    `5`

    </div>

[monday](datetime/monday-constant) → const [int](int-class)

:   <div>

    `1`

    </div>

[monthsPerYear](datetime/monthsperyear-constant) → const [int](int-class)

:   <div>

    `12`

    </div>

[november](datetime/november-constant) → const [int](int-class)

:   <div>

    `11`

    </div>

[october](datetime/october-constant) → const [int](int-class)

:   <div>

    `10`

    </div>

[saturday](datetime/saturday-constant) → const [int](int-class)

:   <div>

    `6`

    </div>

[september](datetime/september-constant) → const [int](int-class)

:   <div>

    `9`

    </div>

[sunday](datetime/sunday-constant) → const [int](int-class)

:   <div>

    `7`

    </div>

[thursday](datetime/thursday-constant) → const [int](int-class)

:   <div>

    `4`

    </div>

[tuesday](datetime/tuesday-constant) → const [int](int-class)

:   <div>

    `2`

    </div>

[wednesday](datetime/wednesday-constant) → const [int](int-class)

:   <div>

    `3`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime-class.html>
:::
