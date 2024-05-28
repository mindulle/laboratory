[dart:core](../dart-core/dart-core-library){._links-link}

Duration class
==============

A span of time, such as 27 days, 4 hours, 12 minutes, and 3 seconds.

A `Duration` represents a difference from one point in time to another.
The duration may be \"negative\" if the difference is from a later time
to an earlier.

Durations are context independent. For example, a duration of 2 days is
always 48 hours, even when it is added to a `DateTime` just when the
time zone is about to make a daylight-savings switch. (See
[DateTime.add](datetime/add)).

Despite the same name, a `Duration` object does not implement
\"Durations\" as specified by ISO 8601. In particular, a duration object
does not keep track of the individually provided members (such as
\"days\" or \"hours\"), but only uses these arguments to compute the
length of the corresponding time interval.

To create a new `Duration` object, use this class\'s single constructor
giving the appropriate arguments:

``` {.language-dart data-language="dart"}
const fastestMarathon = Duration(hours: 2, minutes: 3, seconds: 2);
```

The [Duration](duration-class) represents a single number of
microseconds, which is the sum of all the individual arguments to the
constructor.

Properties can access that single number in different ways. For example
the [inMinutes](duration/inminutes) gives the number of whole minutes in
the total duration, which includes the minutes that were provided as
\"hours\" to the constructor, and can be larger than 59.

``` {.language-dart data-language="dart"}
const fastestMarathon = Duration(hours: 2, minutes: 3, seconds: 2);
print(fastestMarathon.inDays); // 0
print(fastestMarathon.inHours); // 2
print(fastestMarathon.inMinutes); // 123
print(fastestMarathon.inSeconds); // 7382
print(fastestMarathon.inMilliseconds); // 7382000
```

The duration can be negative, in which case all the properties derived
from the duration are also non-positive.

``` {.language-dart data-language="dart"}
const overDayAgo = Duration(days: -1, hours: -10);
print(overDayAgo.inDays); // -1
print(overDayAgo.inHours); // -34
print(overDayAgo.inMinutes); // -2040
```

Use one of the properties, such as [inDays](duration/indays), to
retrieve the integer value of the `Duration` in the specified time unit.
Note that the returned value is rounded down. For example,

``` {.language-dart data-language="dart"}
const aLongWeekend = Duration(hours: 88);
print(aLongWeekend.inDays); // 3
```

This class provides a collection of arithmetic and comparison operators,
plus a set of constants useful for converting time units.

``` {.language-dart data-language="dart"}
const firstHalf = Duration(minutes: 45); // 00:45:00.000000
const secondHalf = Duration(minutes: 45); // 00:45:00.000000
const overTime = Duration(minutes: 30); // 00:30:00.000000
final maxGameTime = firstHalf + secondHalf + overTime;
print(maxGameTime.inMinutes); // 120

// The duration of the firstHalf and secondHalf is the same, returns 0.
var result = firstHalf.compareTo(secondHalf);
print(result); // 0

// Duration of overTime is shorter than firstHalf, returns < 0.
result = overTime.compareTo(firstHalf);
print(result); // < 0

// Duration of secondHalf is longer than overTime, returns > 0.
result = secondHalf.compareTo(overTime);
print(result); // > 0
```

**See also:**

-   [DateTime](datetime-class) to represent a point in time.
-   [Stopwatch](stopwatch-class) to measure time-spans.

Implemented types

:   -   [Comparable](comparable-class)\<[Duration](duration-class)\>

Constructors
------------

[Duration](duration/duration)({[int](int-class) days = 0,
[int](int-class) hours = 0, [int](int-class) minutes = 0,
[int](int-class) seconds = 0, [int](int-class) milliseconds = 0,
[int](int-class) microseconds = 0})

::: {.constructor-modifier .features}
const
:::

Creates a new [Duration](duration-class) object whose value is the sum
of all individual parts.

Properties {#instance-properties}
----------

[hashCode](duration/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

The hash code for this object.

[inDays](duration/indays) → [int](int-class)

::: {.features}
read-only
:::

The number of entire days spanned by this [Duration](duration-class).

[inHours](duration/inhours) → [int](int-class)

::: {.features}
read-only
:::

The number of entire hours spanned by this [Duration](duration-class).

[inMicroseconds](duration/inmicroseconds) → [int](int-class)

::: {.features}
read-only
:::

The number of whole microseconds spanned by this
[Duration](duration-class).

[inMilliseconds](duration/inmilliseconds) → [int](int-class)

::: {.features}
read-only
:::

The number of whole milliseconds spanned by this
[Duration](duration-class).

[inMinutes](duration/inminutes) → [int](int-class)

::: {.features}
read-only
:::

The number of whole minutes spanned by this [Duration](duration-class).

[inSeconds](duration/inseconds) → [int](int-class)

::: {.features}
read-only
:::

The number of whole seconds spanned by this [Duration](duration-class).

[isNegative](duration/isnegative) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this [Duration](duration-class) is negative.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[abs](duration/abs)() → [Duration](duration-class)

Creates a new [Duration](duration-class) representing the absolute
length of this [Duration](duration-class).

[compareTo](duration/compareto)([Duration](duration-class) other) →
[int](int-class)

::: {.features}
override
:::

Compares this [Duration](duration-class) to `other`, returning zero if
the values are equal.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](duration/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns a string representation of this [Duration](duration-class).

Operators
---------

[operator \*](duration/operator_multiply)([num](num-class) factor) →
[Duration](duration-class)

Multiplies this Duration by the given `factor` and returns the result as
a new Duration object.

[operator +](duration/operator_plus)([Duration](duration-class) other) →
[Duration](duration-class)

Adds this Duration and `other` and returns the sum as a new Duration
object.

[operator -](duration/operator_minus)([Duration](duration-class) other)
→ [Duration](duration-class)

Subtracts `other` from this Duration and returns the difference as a new
Duration object.

[operator \<](duration/operator_less)([Duration](duration-class) other)
→ [bool](bool-class)

Whether this [Duration](duration-class) is shorter than `other`.

[operator \<=](duration/operator_less_equal)([Duration](duration-class)
other) → [bool](bool-class)

Whether this [Duration](duration-class) is shorter than or equal to
`other`.

[operator ==](duration/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

Whether this [Duration](duration-class) has the same length as `other`.

[operator \>](duration/operator_greater)([Duration](duration-class)
other) → [bool](bool-class)

Whether this [Duration](duration-class) is longer than `other`.

[operator
\>=](duration/operator_greater_equal)([Duration](duration-class) other)
→ [bool](bool-class)

Whether this [Duration](duration-class) is longer than or equal to
`other`.

[operator unary-](duration/operator_unary_minus)() →
[Duration](duration-class)

Creates a new [Duration](duration-class) with the opposite direction of
this [Duration](duration-class).

[operator \~/](duration/operator_truncate_divide)([int](int-class)
quotient) → [Duration](duration-class)

Divides this Duration by the given `quotient` and returns the truncated
result as a new Duration object.

Constants
---------

[hoursPerDay](duration/hoursperday-constant) → const [int](int-class)
:   The number of hours per day.
    <div>

    `24`

    </div>

[microsecondsPerDay](duration/microsecondsperday-constant) → const [int](int-class)
:   The number of microseconds per day.
    <div>

    `microsecondsPerHour * hoursPerDay`

    </div>

[microsecondsPerHour](duration/microsecondsperhour-constant) → const [int](int-class)
:   The number of microseconds per hour.
    <div>

    `microsecondsPerMinute * minutesPerHour`

    </div>

[microsecondsPerMillisecond](duration/microsecondspermillisecond-constant) → const [int](int-class)
:   The number of microseconds per millisecond.
    <div>

    `1000`

    </div>

[microsecondsPerMinute](duration/microsecondsperminute-constant) → const [int](int-class)
:   The number of microseconds per minute.
    <div>

    `microsecondsPerSecond * secondsPerMinute`

    </div>

[microsecondsPerSecond](duration/microsecondspersecond-constant) → const [int](int-class)
:   The number of microseconds per second.
    <div>

    `microsecondsPerMillisecond * millisecondsPerSecond`

    </div>

[millisecondsPerDay](duration/millisecondsperday-constant) → const [int](int-class)
:   The number of milliseconds per day.
    <div>

    `millisecondsPerHour * hoursPerDay`

    </div>

[millisecondsPerHour](duration/millisecondsperhour-constant) → const [int](int-class)
:   The number of milliseconds per hour.
    <div>

    `millisecondsPerMinute * minutesPerHour`

    </div>

[millisecondsPerMinute](duration/millisecondsperminute-constant) → const [int](int-class)
:   The number of milliseconds per minute.
    <div>

    `millisecondsPerSecond * secondsPerMinute`

    </div>

[millisecondsPerSecond](duration/millisecondspersecond-constant) → const [int](int-class)
:   The number of milliseconds per second.
    <div>

    `1000`

    </div>

[minutesPerDay](duration/minutesperday-constant) → const [int](int-class)
:   The number of minutes per day.
    <div>

    `minutesPerHour * hoursPerDay`

    </div>

[minutesPerHour](duration/minutesperhour-constant) → const [int](int-class)
:   The number of minutes per hour.
    <div>

    `60`

    </div>

[secondsPerDay](duration/secondsperday-constant) → const [int](int-class)
:   The number of seconds per day.
    <div>

    `secondsPerHour * hoursPerDay`

    </div>

[secondsPerHour](duration/secondsperhour-constant) → const [int](int-class)
:   The number of seconds per hour.
    <div>

    `secondsPerMinute * minutesPerHour`

    </div>

[secondsPerMinute](duration/secondsperminute-constant) → const [int](int-class)
:   The number of seconds per minute.
    <div>

    `60`

    </div>

[zero](duration/zero-constant) → const [Duration](duration-class)
:   An empty duration, representing zero time.
    <div>

    `Duration(seconds: 0)`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration-class.html>
:::
