[dart:io](../../dart-io/dart-io-library){._links-link}

enableTimelineLogging property
==============================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) enableTimelineLogging
:::

Current state of HTTP request logging from all
[HttpClient](../httpclient-class)s to the developer timeline.

Default is `false`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get enableTimelineLogging => _enableTimelineLogging;
```

::: {#setter .section .multi-line-signature}
void enableTimelineLogging=([bool](../../dart-core/bool-class) value)
:::

Enable logging of HTTP requests from all
[HttpClient](../httpclient-class)s to the developer timeline.

Default is `false`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static set enableTimelineLogging(bool value) {
  final enabled = valueOfNonNullableParamWithDefault<bool>(value, false);
  if (enabled != _enableTimelineLogging) {
    postEvent('HttpTimelineLoggingStateChange', {
      'isolateId': Service.getIsolateID(Isolate.current),
      'enabled': enabled,
    });
  }
  _enableTimelineLogging = enabled;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/enableTimelineLogging.html>
:::
