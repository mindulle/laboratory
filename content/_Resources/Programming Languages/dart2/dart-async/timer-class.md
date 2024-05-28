[dart:async](../dart-async/dart-async-library){._links-link}

Timer class
===========

A countdown timer that can be configured to fire once or repeatedly.

The timer counts down from the specified duration to 0. When the timer
reaches 0, the timer invokes the specified callback function. Use a
periodic timer to repeatedly count down the same interval.

A negative duration is treated the same as a duration of 0. If the
duration is statically known to be 0, consider using [run](timer/run).

Frequently the duration is either a constant or computed as in the
following example (taking advantage of the multiplication operator of
the [Duration](../dart-core/duration-class) class):

``` {.language-dart data-language="dart"}
void main() {
  scheduleTimeout(5 * 1000); // 5 seconds.
}

Timer scheduleTimeout([int milliseconds = 10000]) =>
    Timer(Duration(milliseconds: milliseconds), handleTimeout);

void handleTimeout() {  // callback function
  // Do some work.
}
```

**Note:** If Dart code using [Timer](timer-class) is compiled to
JavaScript, the finest granularity available in the browser is 4
milliseconds.

See also:

-   [Stopwatch](../dart-core/stopwatch-class) for measuring elapsed
    time.

Constructors
------------

[Timer](timer/timer)([Duration](../dart-core/duration-class) duration,
void callback())

::: {.constructor-modifier .features}
factory
:::

Creates a new timer.

[Timer.periodic](timer/timer.periodic)([Duration](../dart-core/duration-class)
duration, void callback([Timer](timer-class) timer))

::: {.constructor-modifier .features}
factory
:::

Creates a new repeating timer.

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isActive](timer/isactive) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Returns whether the timer is still active.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[tick](timer/tick) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The number of durations preceding the most recent timer event.

Methods {#instance-methods}
-------

[cancel](timer/cancel)() → void

Cancels the timer.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[run](timer/run)(void callback()) → void
:   Runs the given `callback` asynchronously as soon as possible.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Timer-class.html>
:::
