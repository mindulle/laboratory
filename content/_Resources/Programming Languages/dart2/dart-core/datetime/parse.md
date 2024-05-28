[dart:core](../../dart-core/dart-core-library){._links-link}

parse method
============

::: {.section .multi-line-signature}
[DateTime](../datetime-class) parse(

1.  [String](../string-class) formattedString

)
:::

Constructs a new [DateTime](../datetime-class) instance based on
`formattedString`.

Throws a [FormatException](../formatexception-class) if the input string
cannot be parsed.

The function parses a subset of ISO 8601, which includes the subset
accepted by RFC 3339.

The accepted inputs are currently:

-   A date: A signed four-to-six digit year, two digit month and two
    digit day, optionally separated by `-` characters. Examples:
    \"19700101\", \"-0004-12-24\", \"81030-04-01\".
-   An optional time part, separated from the date by either `T` or a
    space. The time part is a two digit hour, then optionally a two
    digit minutes value, then optionally a two digit seconds value, and
    then optionally a \'.\' or \',\' followed by at least a one digit
    second fraction. The minutes and seconds may be separated from the
    previous parts by a \':\'. Examples: \"12\", \"12:30:24.124\",
    \"12:30:24,124\", \"123010.50\".
-   An optional time-zone offset part, possibly separated from the
    previous by a space. The time zone is either \'z\' or \'Z\', or it
    is a signed two digit hour part and an optional two digit minute
    part. The sign must be either \"+\" or \"-\", and cannot be omitted.
    The minutes may be separated from the hours by a \':\'. Examples:
    \"Z\", \"-10\", \"+01:30\", \"+1130\".

This includes the output of both [toString](tostring) and
[toIso8601String](toiso8601string), which will be parsed back into a
`DateTime` object with the same time as the original.

The result is always in either local time or UTC. If a time zone offset
other than UTC is specified, the time is converted to the equivalent UTC
time.

Examples of accepted strings:

-   `"2012-02-27"`
-   `"2012-02-27 13:27:00"`
-   `"2012-02-27 13:27:00.123456789z"`
-   `"2012-02-27 13:27:00,123456789z"`
-   `"20120227 13:27:00"`
-   `"20120227T132700"`
-   `"20120227"`
-   `"+20120227"`
-   `"2012-02-27T14Z"`
-   `"2012-02-27T14+00:00"`
-   `"-123450101 00:00:00 Z"`: in the year -12345.
-   `"2002-02-27T14:00:00-0500"`: Same as `"2002-02-27T19:00:00Z"`

This method accepts out-of-range component values and interprets them as
overflows into the next larger component. For example, \"2020-01-42\"
will be parsed as 2020-02-11, because the last valid date in that month
is 2020-01-31, so 42 days is interpreted as 31 days of that month plus
11 days into the next month.

To detect and reject invalid component values, use
[DateFormat.parseStrict](https://pub.dev/documentation/intl/latest/intl/DateFormat/parseStrict.html)
from the [intl](https://pub.dev/packages/intl) package.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static DateTime parse(String formattedString) {
  var re = _parseFormat;
  Match? match = re.firstMatch(formattedString);
  if (match != null) {
    int parseIntOrZero(String? matched) {
      if (matched == null) return 0;
      return int.parse(matched);
    }

    // Parses fractional second digits of '.(\d+)' into the combined
    // microseconds. We only use the first 6 digits because of DateTime
    // precision of 999 milliseconds and 999 microseconds.
    int parseMilliAndMicroseconds(String? matched) {
      if (matched == null) return 0;
      int length = matched.length;
      assert(length >= 1);
      int result = 0;
      for (int i = 0; i < 6; i++) {
        result *= 10;
        if (i < matched.length) {
          result += matched.codeUnitAt(i) ^ 0x30;
        }
      }
      return result;
    }

    int years = int.parse(match[1]!);
    int month = int.parse(match[2]!);
    int day = int.parse(match[3]!);
    int hour = parseIntOrZero(match[4]);
    int minute = parseIntOrZero(match[5]);
    int second = parseIntOrZero(match[6]);
    int milliAndMicroseconds = parseMilliAndMicroseconds(match[7]);
    int millisecond =
        milliAndMicroseconds ~/ Duration.microsecondsPerMillisecond;
    int microsecond = milliAndMicroseconds
        .remainder(Duration.microsecondsPerMillisecond) as int;
    bool isUtc = false;
    if (match[8] != null) {
      // timezone part
      isUtc = true;
      String? tzSign = match[9];
      if (tzSign != null) {
        // timezone other than 'Z' and 'z'.
        int sign = (tzSign == '-') ? -1 : 1;
        int hourDifference = int.parse(match[10]!);
        int minuteDifference = parseIntOrZero(match[11]);
        minuteDifference += 60 * hourDifference;
        minute -= sign * minuteDifference;
      }
    }
    int? value = _brokenDownDateToValue(years, month, day, hour, minute,
        second, millisecond, microsecond, isUtc);
    if (value == null) {
      throw FormatException("Time out of range", formattedString);
    }
    return DateTime._withValue(value, isUtc: isUtc);
  } else {
    throw FormatException("Invalid date format", formattedString);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/parse.html>
:::
