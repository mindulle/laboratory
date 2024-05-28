[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

decodeAudioData method
======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[AudioBuffer](../audiobuffer-class)\>
decodeAudioData(

1.  [ByteBuffer](../../dart-typed_data/bytebuffer-class) audioData,
2.  \[[DecodeSuccessCallback](../../dart-html/decodesuccesscallback)?
    successCallback,
3.  [DecodeErrorCallback](../../dart-html/decodeerrorcallback)?
    errorCallback\]

)

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<AudioBuffer> decodeAudioData(ByteBuffer audioData,
    [DecodeSuccessCallback? successCallback,
    DecodeErrorCallback? errorCallback]) {
  // Both callbacks need to be provided if they're being used.
  assert((successCallback == null) == (errorCallback == null));
  // `decodeAudioData` can exist either in the older callback syntax or the
  // newer `Promise`-based syntax that also accepts callbacks. In the former,
  // we synthesize a `Future` to be consistent.
  // For more details:
  // https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/decodeAudioData
  // https://www.w3.org/TR/webaudio/#dom-baseaudiocontext-decodeaudiodata
  final completer = Completer<Object>();
  var errorInCallbackIsNull = false;

  void success(AudioBuffer decodedData) {
    completer.complete(decodedData);
    successCallback!.call(decodedData);
  }

  final nullErrorString =
      '[AudioContext.decodeAudioData] completed with a null error.';

  void error(DomException? error) {
    // Safari has a bug where it may return null for the error callback. In
    // the case where the Safari version still returns a `Promise` and the
    // error is not null after the `Promise` is finished, the error callback
    // is called instead in the `Promise`'s `catch` block. Otherwise, and in
    // the case where a `Promise` is not returned by the API at all, the
    // callback never gets called (for backwards compatibility, it can not
    // accept null). Instead, the `Future` completes with a custom string,
    // indicating that null was given.
    // https://github.com/mdn/webaudio-examples/issues/5
    if (error != null) {
      // Note that we `complete` and not `completeError`. This is to make sure
      // that errors in the `Completer` are not thrown if the call gets back
      // a `Promise`.
      completer.complete(error);
      errorCallback!.call(error);
    } else {
      completer.complete(nullErrorString);
      errorInCallbackIsNull = true;
    }
  }

  var decodeResult;
  if (successCallback == null) {
    decodeResult =
        JS("creates:AudioBuffer;", "#.decodeAudioData(#)", this, audioData);
  } else {
    decodeResult = JS(
        "creates:AudioBuffer;",
        "#.decodeAudioData(#, #, #)",
        this,
        audioData,
        convertDartClosureToJS(success, 1),
        convertDartClosureToJS(error, 1));
  }

  if (decodeResult != null) {
    // Promise-based syntax.
    return promiseToFuture<AudioBuffer>(decodeResult).catchError((error) {
      // If the error was null in the callback, but no longer is now that the
      // `Promise` is finished, call the error callback. If it's still null,
      // throw the error string. This is to handle the aforementioned bug in
      // Safari.
      if (errorInCallbackIsNull) {
        if (error != null) {
          errorCallback?.call(error);
        } else {
          throw nullErrorString;
        }
      }
      throw error;
    });
  }

  // Callback-based syntax. We use the above completer to synthesize a
  // `Future` from the callback values. Since we don't use `completeError`
  // above, `then` is used to simulate an error.
  return completer.future.then((value) {
    if (value is AudioBuffer) return value;
    throw value;
  });
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioContext/decodeAudioData.html>
:::
