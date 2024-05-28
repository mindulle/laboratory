[dart:io](../../dart-io/dart-io-library){._links-link}

parse method
============

::: {.section .multi-line-signature}
[DateTime](../../dart-core/datetime-class) parse(

1.  [String](../../dart-core/string-class) date

)
:::

Parse a date string in either of the formats
[RFC-1123](http://tools.ietf.org/html/rfc1123 "RFC-1123"),
[RFC-850](http://tools.ietf.org/html/rfc850 "RFC-850") or ANSI C\'s
asctime() format. These formats are listed here.

``` {.language-dart data-language="dart"}
Thu, 1 Jan 1970 00:00:00 GMT
Thursday, 1-Jan-1970 00:00:00 GMT
Thu Jan  1 00:00:00 1970
```

For more information see [RFC-2616 section
3.1.1](http://tools.ietf.org/html/rfc2616#section-3.3.1 "RFC-2616 section 3.1.1").

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static DateTime parse(String date) {
  final int SP = 32;
  const List wkdays = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"];
  const List weekdays = [
    "Monday",
    "Tuesday",
    "Wednesday",
    "Thursday",
    "Friday",
    "Saturday",
    "Sunday"
  ];
  const List months = [
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

  final int formatRfc1123 = 0;
  final int formatRfc850 = 1;
  final int formatAsctime = 2;

  int index = 0;
  String tmp;

  void expect(String s) {
    if (date.length - index < s.length) {
      throw HttpException("Invalid HTTP date $date");
    }
    String tmp = date.substring(index, index + s.length);
    if (tmp != s) {
      throw HttpException("Invalid HTTP date $date");
    }
    index += s.length;
  }

  int expectWeekday() {
    int weekday;
    // The formatting of the weekday signals the format of the date string.
    int pos = date.indexOf(",", index);
    if (pos == -1) {
      int pos = date.indexOf(" ", index);
      if (pos == -1) throw HttpException("Invalid HTTP date $date");
      tmp = date.substring(index, pos);
      index = pos + 1;
      weekday = wkdays.indexOf(tmp);
      if (weekday != -1) {
        return formatAsctime;
      }
    } else {
      tmp = date.substring(index, pos);
      index = pos + 1;
      weekday = wkdays.indexOf(tmp);
      if (weekday != -1) {
        return formatRfc1123;
      }
      weekday = weekdays.indexOf(tmp);
      if (weekday != -1) {
        return formatRfc850;
      }
    }
    throw HttpException("Invalid HTTP date $date");
  }

  int expectMonth(String separator) {
    int pos = date.indexOf(separator, index);
    if (pos - index != 3) throw HttpException("Invalid HTTP date $date");
    tmp = date.substring(index, pos);
    index = pos + 1;
    int month = months.indexOf(tmp);
    if (month != -1) return month;
    throw HttpException("Invalid HTTP date $date");
  }

  int expectNum(String separator) {
    int pos;
    if (separator.isNotEmpty) {
      pos = date.indexOf(separator, index);
    } else {
      pos = date.length;
    }
    String tmp = date.substring(index, pos);
    index = pos + separator.length;
    try {
      int value = int.parse(tmp);
      return value;
    } on FormatException {
      throw HttpException("Invalid HTTP date $date");
    }
  }

  void expectEnd() {
    if (index != date.length) {
      throw HttpException("Invalid HTTP date $date");
    }
  }

  int format = expectWeekday();
  int year;
  int month;
  int day;
  int hours;
  int minutes;
  int seconds;
  if (format == formatAsctime) {
    month = expectMonth(" ");
    if (date.codeUnitAt(index) == SP) index++;
    day = expectNum(" ");
    hours = expectNum(":");
    minutes = expectNum(":");
    seconds = expectNum(" ");
    year = expectNum("");
  } else {
    expect(" ");
    day = expectNum(format == formatRfc1123 ? " " : "-");
    month = expectMonth(format == formatRfc1123 ? " " : "-");
    year = expectNum(" ");
    hours = expectNum(":");
    minutes = expectNum(":");
    seconds = expectNum(" ");
    expect("GMT");
  }
  expectEnd();
  return DateTime.utc(year, month + 1, day, hours, minutes, seconds, 0);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpDate/parse.html>
:::
