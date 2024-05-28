[dart:core](../../dart-core/dart-core-library){._links-link}

timeZoneOffset property
=======================

::: {#getter .section .multi-line-signature}
[Duration](../duration-class) timeZoneOffset
:::

The time zone offset, which is the difference between local time and
UTC.

The offset is positive for time zones east of UTC.

Note, that JavaScript, Python and C return the difference between UTC
and local time. Java, C\# and Ruby return the difference between local
time and UTC.

For example, using local time in San Francisco, United States:

``` {.language-dart data-language="dart"}
final dateUS = DateTime.parse('2021-11-01 20:18:04Z').toLocal();
print(dateUS); // 2021-11-01 13:18:04.000
print(dateUS.timeZoneName); // PDT ( Pacific Daylight Time )
print(dateUS.timeZoneOffset.inHours); // -7
print(dateUS.timeZoneOffset.inMinutes); // -420
```

For example, using local time in Canberra, Australia:

``` {.language-dart data-language="dart"}
final dateAus = DateTime.parse('2021-11-01 20:18:04Z').toLocal();
print(dateAus); // 2021-11-02 07:18:04.000
print(dateAus.timeZoneName); // AEDT ( Australian Eastern Daylight Time )
print(dateAus.timeZoneOffset.inHours); // 11
print(dateAus.timeZoneOffset.inMinutes); // 660
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Duration get timeZoneOffset;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/timeZoneOffset.html>
:::
