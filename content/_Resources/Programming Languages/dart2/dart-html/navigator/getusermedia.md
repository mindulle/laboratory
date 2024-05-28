[dart:html](../../dart-html/dart-html-library){._links-link}

getUserMedia method
===================

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME)

</div>

[Future](../../dart-async/future-class)\<[MediaStream](../mediastream-class)\>
getUserMedia(

1.  {dynamic audio = false,
2.  dynamic video = false}

)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME)
:::
:::

Gets a stream (video and or audio) from the local computer.

Use [MediaStream.supported](../mediastream/supported) to check if this
is supported by the current platform. The arguments `audio` and `video`
default to `false` (stream does not use audio or video, respectively).

Simple example usage:

``` {.language-dart data-language="dart"}
window.navigator.getUserMedia(audio: true, video: true).then((stream) {
  var video = new VideoElement()
    ..autoplay = true
    ..src = Url.createObjectUrlFromStream(stream);
  document.body.append(video);
});
```

The user can also pass in Maps to the audio or video parameters to
specify mandatory and optional constraints for the media stream. Not
passing in a map, but passing in `true` will provide a MediaStream with
audio or video capabilities, but without any additional constraints. The
particular constraint names for audio and video are still in flux, but
as of this writing, here is an example providing more constraints.

``` {.language-dart data-language="dart"}
window.navigator.getUserMedia(
    audio: true,
    video: {'mandatory':
               { 'minAspectRatio': 1.333, 'maxAspectRatio': 1.334 },
            'optional':
               [{ 'minFrameRate': 60 },
                { 'maxWidth': 640 }]
});
```

See also:

-   [MediaStream.supported](../mediastream/supported)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
Future<MediaStream> getUserMedia({audio: false, video: false}) {
  var completer = new Completer<MediaStream>();
  var options = {'audio': audio, 'video': video};
  _ensureGetUserMedia();
  this._getUserMedia(convertDartToNative_SerializedScriptValue(options),
      (stream) {
    completer.complete(stream);
  }, (error) {
    completer.completeError(error);
  });
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Navigator/getUserMedia.html>
:::
