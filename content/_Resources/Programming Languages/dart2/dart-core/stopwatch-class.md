[dart:core](../dart-core/dart-core-library){._links-link}

Stopwatch class
===============

A stopwatch which measures time while it\'s running.

A stopwatch is either running or stopped. It measures the elapsed time
that passes while the stopwatch is running.

When a stopwatch is initially created, it is stopped and has measured no
elapsed time.

The elapsed time can be accessed in various formats using
[elapsed](stopwatch/elapsed),
[elapsedMilliseconds](stopwatch/elapsedmilliseconds),
[elapsedMicroseconds](stopwatch/elapsedmicroseconds) or
[elapsedTicks](stopwatch/elapsedticks).

The stopwatch is started by calling [start](stopwatch/start).

Example:

``` {.language-dart data-language="dart"}
final stopwatch = Stopwatch();
print(stopwatch.elapsedMilliseconds); // 0
print(stopwatch.isRunning); // false
stopwatch.start();
print(stopwatch.isRunning); // true
```

To stop or pause the stopwatch, use [stop](stopwatch/stop). Use
[start](stopwatch/start) to continue again when only pausing
temporarily.

``` {.language-dart data-language="dart"}
stopwatch.stop();
print(stopwatch.isRunning); // false
Duration elapsed = stopwatch.elapsed;
await Future.delayed(const Duration(seconds: 1));
assert(stopwatch.elapsed == elapsed); // No measured time elapsed.
stopwatch.start(); // Continue measuring.
```

The [reset](stopwatch/reset) method sets the elapsed time back to zero.
It can be called whether the stopwatch is running or not, and doesn\'t
change whether it\'s running.

``` {.language-dart data-language="dart"}
// Do some work.
stopwatch.stop();
print(stopwatch.elapsedMilliseconds); // Likely > 0.
stopwatch.reset();
print(stopwatch.elapsedMilliseconds); // 0
```

Constructors
------------

[Stopwatch](stopwatch/stopwatch)()
:   Creates a [Stopwatch](stopwatch-class) in stopped state with a zero
    elapsed count.

Properties {#instance-properties}
----------

[elapsed](stopwatch/elapsed) → [Duration](duration-class)

::: {.features}
read-only
:::

The [elapsedTicks](stopwatch/elapsedticks) counter converted to a
[Duration](duration-class).

[elapsedMicroseconds](stopwatch/elapsedmicroseconds) → [int](int-class)

::: {.features}
read-only
:::

The [elapsedTicks](stopwatch/elapsedticks) counter converted to
microseconds.

[elapsedMilliseconds](stopwatch/elapsedmilliseconds) → [int](int-class)

::: {.features}
read-only
:::

The [elapsedTicks](stopwatch/elapsedticks) counter converted to
milliseconds.

[elapsedTicks](stopwatch/elapsedticks) → [int](int-class)

::: {.features}
read-only
:::

The elapsed number of clock ticks since calling [start](stopwatch/start)
while the [Stopwatch](stopwatch-class) is running.

[frequency](stopwatch/frequency) → [int](int-class)

::: {.features}
read-only
:::

Frequency of the elapsed counter in Hz.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isRunning](stopwatch/isrunning) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the [Stopwatch](stopwatch-class) is currently running.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reset](stopwatch/reset)() → void

Resets the [elapsed](stopwatch/elapsed) count to zero.

[start](stopwatch/start)() → void

Starts the [Stopwatch](stopwatch-class).

[stop](stopwatch/stop)() → void

Stops the [Stopwatch](stopwatch-class).

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Stopwatch-class.html>
:::
