[dart:html](../../dart-html/dart-html-library){._links-link}

watchPosition method
====================

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Geoposition](../geoposition-class)\>
watchPosition(

1.  {[bool](../../dart-core/bool-class)? enableHighAccuracy,
2.  [Duration](../../dart-core/duration-class)? timeout,
3.  [Duration](../../dart-core/duration-class)? maximumAge}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Geoposition> watchPosition(
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

  int? watchId;
  StreamController<Geoposition> controller =
      new StreamController<Geoposition>(
          sync: true,
          onCancel: () {
            assert(watchId != null);
            _clearWatch(watchId!);
          });
  controller.onListen = () {
    assert(watchId == null);
    watchId = _watchPosition((position) {
      controller.add(_ensurePosition(position));
    }, (error) {
      controller.addError(error);
    }, options);
  };

  return controller.stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Geolocation/watchPosition.html>
:::
