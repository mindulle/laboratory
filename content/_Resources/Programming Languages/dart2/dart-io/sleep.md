[dart:io](../dart-io/dart-io-library){._links-link}

sleep function
==============

::: {.section .multi-line-signature}
void sleep(

1.  [Duration](../dart-core/duration-class) duration

)
:::

Sleep for the duration specified in `duration`.

Use this with care, as no asynchronous operations can be processed in a
isolate while it is blocked in a [sleep](sleep) call.

``` {.language-dart data-language="dart"}
var duration = const Duration(seconds: 5);
print('Start sleeping');
sleep(duration);
print('5 seconds has passed');
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void sleep(Duration duration) {
  int milliseconds = duration.inMilliseconds;
  if (milliseconds < 0) {
    throw new ArgumentError("sleep: duration cannot be negative");
  }
  if (!_EmbedderConfig._maySleep) {
    throw new UnsupportedError(
        "This embedder disallows calling dart:io's sleep()");
  }
  _ProcessUtils._sleep(milliseconds);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/sleep.html>
:::
