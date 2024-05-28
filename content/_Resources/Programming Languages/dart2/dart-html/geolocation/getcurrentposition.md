[dart:html](../../dart-html/dart-html-library){._links-link}

getCurrentPosition method
=========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Geoposition](../geoposition-class)\>
getCurrentPosition(

1.  {[bool](../../dart-core/bool-class)? enableHighAccuracy,
2.  [Duration](../../dart-core/duration-class)? timeout,
3.  [Duration](../../dart-core/duration-class)? maximumAge}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Geoposition> getCurrentPosition(
    {bool? enableHighAccuracy, Duration? timeout, Duration? maximumAge}) {
  var options = {};
  if (enableHighAccuracy != null) {
    options['enableHighAccuracy'] = enableHighAccuracy;
  }
  if (timeout != null) {
    options['timeout'] = timeout.inMilliseconds;
  }
  if (maximumAge != null) {
    options['maximumAge'] = maximumAge.inMilliseconds;
  }
  var completer = new Completer<Geoposition>();
  try {
    _getCurrentPosition((position) {
      completer.complete(_ensurePosition(position));
    }, (error) {
      completer.completeError(error);
    }, options);
  } catch (e, stacktrace) {
    completer.completeError(e, stacktrace);
  }
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Geolocation/getCurrentPosition.html>
:::
