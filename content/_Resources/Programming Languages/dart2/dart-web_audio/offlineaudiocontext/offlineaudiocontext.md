[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

OfflineAudioContext constructor
===============================

::: {.section .multi-line-signature}
OfflineAudioContext(

1.  dynamic numberOfChannels\_OR\_options,
2.  \[[int](../../dart-core/int-class)? numberOfFrames,
3.  [num](../../dart-core/num-class)? sampleRate\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory OfflineAudioContext(numberOfChannels_OR_options,
    [int? numberOfFrames, num? sampleRate]) {
  if ((sampleRate is num) &&
      (numberOfFrames is int) &&
      (numberOfChannels_OR_options is int)) {
    return OfflineAudioContext._create_1(
        numberOfChannels_OR_options, numberOfFrames, sampleRate);
  }
  if ((numberOfChannels_OR_options is Map) &&
      numberOfFrames == null &&
      sampleRate == null) {
    var options_1 =
        convertDartToNative_Dictionary(numberOfChannels_OR_options);
    return OfflineAudioContext._create_2(options_1);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/OfflineAudioContext/OfflineAudioContext.html>
:::
