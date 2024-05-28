[dart:developer](../dart-developer/dart-developer-library){._links-link}

log function
============

::: {.section .multi-line-signature}
void log(

1.  [String](../dart-core/string-class) message,
2.  {[DateTime](../dart-core/datetime-class)? time,
3.  [int](../dart-core/int-class)? sequenceNumber,
4.  [int](../dart-core/int-class) level = 0,
5.  [String](../dart-core/string-class) name = \'\',
6.  [Zone](../dart-async/zone-class)? zone,
7.  [Object](../dart-core/object-class)? error,
8.  [StackTrace](../dart-core/stacktrace-class)? stackTrace}

)
:::

Emit a log event.

This function was designed to map closely to the logging information
collected by `package:logging`.

-   `message` is the log message
-   `time` (optional) is the timestamp
-   `sequenceNumber` (optional) is a monotonically increasing sequence
    number
-   `level` (optional) is the severity level (a value between 0 and
    2000); see the `package:logging` `Level` class for an overview of
    the possible values
-   `name` (optional) is the name of the source of the log message
-   `zone` (optional) the zone where the log was emitted
-   `error` (optional) an error object associated with this log event
-   `stackTrace` (optional) a stack trace associated with this log event

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void log(
  String message, {
  DateTime? time,
  int? sequenceNumber,
  int level = 0,
  String name = '',
  Zone? zone,
  Object? error,
  StackTrace? stackTrace,
});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/log.html>
:::
