[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

createPeriodicWave method
=========================

::: {.section .multi-line-signature}
[PeriodicWave](../periodicwave-class) createPeriodicWave(

1.  [List](../../dart-core/list-class)\<[num](../../dart-core/num-class)\>
    real,
2.  [List](../../dart-core/list-class)\<[num](../../dart-core/num-class)\>
    imag,
3.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
PeriodicWave createPeriodicWave(List<num> real, List<num> imag,
    [Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return _createPeriodicWave_1(real, imag, options_1);
  }
  return _createPeriodicWave_2(real, imag);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/BaseAudioContext/createPeriodicWave.html>
:::
