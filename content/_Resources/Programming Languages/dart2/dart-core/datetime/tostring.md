[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

Returns a human-readable string for this instance.

The returned string is constructed for the time zone of this instance.
The `toString()` method provides a simply formatted string. It does not
support internationalized strings. Use the
[intl](https://pub.dev/packages/intl) package at the pub shared packages
repo.

The resulting string can be parsed back using [parse](parse).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() {
  String y = _fourDigits(year);
  String m = _twoDigits(month);
  String d = _twoDigits(day);
  String h = _twoDigits(hour);
  String min = _twoDigits(minute);
  String sec = _twoDigits(second);
  String ms = _threeDigits(millisecond);
  String us = microsecond == 0 ? "" : _threeDigits(microsecond);
  if (isUtc) {
    return "$y-$m-$d $h:$min:$sec.$ms${us}Z";
  } else {
    return "$y-$m-$d $h:$min:$sec.$ms$us";
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/toString.html>
:::
