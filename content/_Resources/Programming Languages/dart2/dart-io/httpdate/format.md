[dart:io](../../dart-io/dart-io-library){._links-link}

format method
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) format(

1.  [DateTime](../../dart-core/datetime-class) date

)
:::

Format a date according to
[RFC-1123](http://tools.ietf.org/html/rfc1123 "RFC-1123"), e.g.
`Thu, 1 Jan 1970 00:00:00 GMT`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String format(DateTime date) {
  const List wkday = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"];
  const List month = [
    "Jan",
    "Feb",
    "Mar",
    "Apr",
    "May",
    "Jun",
    "Jul",
    "Aug",
    "Sep",
    "Oct",
    "Nov",
    "Dec"
  ];

  DateTime d = date.toUtc();
  StringBuffer sb = StringBuffer()
    ..write(wkday[d.weekday - 1])
    ..write(", ")
    ..write(d.day <= 9 ? "0" : "")
    ..write(d.day.toString())
    ..write(" ")
    ..write(month[d.month - 1])
    ..write(" ")
    ..write(d.year.toString())
    ..write(d.hour <= 9 ? " 0" : " ")
    ..write(d.hour.toString())
    ..write(d.minute <= 9 ? ":0" : ":")
    ..write(d.minute.toString())
    ..write(d.second <= 9 ? ":0" : ":")
    ..write(d.second.toString())
    ..write(" GMT");
  return sb.toString();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpDate/format.html>
:::
