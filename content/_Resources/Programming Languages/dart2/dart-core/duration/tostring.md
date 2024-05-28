[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

Returns a string representation of this [Duration](../duration-class).

Returns a string with hours, minutes, seconds, and microseconds, in the
following format: `H:MM:SS.mmmmmm`. For example,

``` {.language-dart data-language="dart"}
var d = const Duration(days: 1, hours: 1, minutes: 33, microseconds: 500);
print(d.toString()); // 25:33:00.000500

d = const Duration(hours: 1, minutes: 10, microseconds: 500);
print(d.toString()); // 1:10:00.000500
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() {
  var microseconds = inMicroseconds;
  var sign = (microseconds < 0) ? "-" : "";

  var hours = microseconds ~/ microsecondsPerHour;
  microseconds = microseconds.remainder(microsecondsPerHour);

  if (microseconds < 0) microseconds = -microseconds;

  var minutes = microseconds ~/ microsecondsPerMinute;
  microseconds = microseconds.remainder(microsecondsPerMinute);

  var minutesPadding = minutes < 10 ? "0" : "";

  var seconds = microseconds ~/ microsecondsPerSecond;
  microseconds = microseconds.remainder(microsecondsPerSecond);

  var secondsPadding = seconds < 10 ? "0" : "";

  var paddedMicroseconds = microseconds.toString().padLeft(6, "0");
  return "$sign${hours.abs()}:"
      "$minutesPadding$minutes:"
      "$secondsPadding$seconds.$paddedMicroseconds";
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/toString.html>
:::
