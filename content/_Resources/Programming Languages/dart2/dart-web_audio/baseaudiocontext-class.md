[dart:web\_audio](../dart-web_audio/dart-web_audio-library){._links-link}

BaseAudioContext class
======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](../dart-html/eventtarget-class)
    -   BaseAudioContext

Implementers

:   -   [AudioContext](audiocontext-class)
    -   [OfflineAudioContext](offlineaudiocontext-class)

Annotations

:   -   \@Native(\"BaseAudioContext\")

Properties {#instance-properties}
----------

[currentTime](baseaudiocontext/currenttime) →
[num](../dart-core/num-class)?

::: {.features}
read-only
:::

[destination](baseaudiocontext/destination) →
[AudioDestinationNode](audiodestinationnode-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[listener](baseaudiocontext/listener) →
[AudioListener](audiolistener-class)?

::: {.features}
read-only
:::

[on](../dart-html/eventtarget/on) → [Events](../dart-html/events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sampleRate](baseaudiocontext/samplerate) →
[num](../dart-core/num-class)?

::: {.features}
read-only
:::

[state](baseaudiocontext/state) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[addEventListener](../dart-html/eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](../dart-html/eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[createAnalyser](baseaudiocontext/createanalyser)() →
[AnalyserNode](analysernode-class)

[createBiquadFilter](baseaudiocontext/createbiquadfilter)() →
[BiquadFilterNode](biquadfilternode-class)

[createBuffer](baseaudiocontext/createbuffer)([int](../dart-core/int-class)
numberOfChannels, [int](../dart-core/int-class) numberOfFrames,
[num](../dart-core/num-class) sampleRate) →
[AudioBuffer](audiobuffer-class)

[createBufferSource](baseaudiocontext/createbuffersource)() →
[AudioBufferSourceNode](audiobuffersourcenode-class)

[createChannelMerger](baseaudiocontext/createchannelmerger)(\[[int](../dart-core/int-class)?
numberOfInputs\]) → [ChannelMergerNode](channelmergernode-class)

[createChannelSplitter](baseaudiocontext/createchannelsplitter)(\[[int](../dart-core/int-class)?
numberOfOutputs\]) → [ChannelSplitterNode](channelsplitternode-class)

[createConstantSource](baseaudiocontext/createconstantsource)() →
[ConstantSourceNode](constantsourcenode-class)

[createConvolver](baseaudiocontext/createconvolver)() →
[ConvolverNode](convolvernode-class)

[createDelay](baseaudiocontext/createdelay)(\[[num](../dart-core/num-class)?
maxDelayTime\]) → [DelayNode](delaynode-class)

[createDynamicsCompressor](baseaudiocontext/createdynamicscompressor)()
→ [DynamicsCompressorNode](dynamicscompressornode-class)

[createGain](baseaudiocontext/creategain)() → [GainNode](gainnode-class)

[createIirFilter](baseaudiocontext/createiirfilter)([List](../dart-core/list-class)\<[num](../dart-core/num-class)\>
feedForward,
[List](../dart-core/list-class)\<[num](../dart-core/num-class)\>
feedBack) → [IirFilterNode](iirfilternode-class)

::: {.features}
\@JSName(\'createIIRFilter\')
:::

[createMediaElementSource](baseaudiocontext/createmediaelementsource)([MediaElement](../dart-html/mediaelement-class)
mediaElement) →
[MediaElementAudioSourceNode](mediaelementaudiosourcenode-class)

[createMediaStreamDestination](baseaudiocontext/createmediastreamdestination)()
→
[MediaStreamAudioDestinationNode](mediastreamaudiodestinationnode-class)

[createMediaStreamSource](baseaudiocontext/createmediastreamsource)([MediaStream](../dart-html/mediastream-class)
mediaStream) →
[MediaStreamAudioSourceNode](mediastreamaudiosourcenode-class)

[createOscillator](baseaudiocontext/createoscillator)() →
[OscillatorNode](oscillatornode-class)

[createPanner](baseaudiocontext/createpanner)() →
[PannerNode](pannernode-class)

[createPeriodicWave](baseaudiocontext/createperiodicwave)([List](../dart-core/list-class)\<[num](../dart-core/num-class)\>
real, [List](../dart-core/list-class)\<[num](../dart-core/num-class)\>
imag, \[[Map](../dart-core/map-class)? options\]) →
[PeriodicWave](periodicwave-class)

[createScriptProcessor](baseaudiocontext/createscriptprocessor)(\[[int](../dart-core/int-class)?
bufferSize, [int](../dart-core/int-class)? numberOfInputChannels,
[int](../dart-core/int-class)? numberOfOutputChannels\]) →
[ScriptProcessorNode](scriptprocessornode-class)

[createStereoPanner](baseaudiocontext/createstereopanner)() →
[StereoPannerNode](stereopannernode-class)

[createWaveShaper](baseaudiocontext/createwaveshaper)() →
[WaveShaperNode](waveshapernode-class)

[decodeAudioData](baseaudiocontext/decodeaudiodata)([ByteBuffer](../dart-typed_data/bytebuffer-class)
audioData,
\[[DecodeSuccessCallback](../dart-html/decodesuccesscallback)?
successCallback,
[DecodeErrorCallback](../dart-html/decodeerrorcallback)?
errorCallback\]) →
[Future](../dart-async/future-class)\<[AudioBuffer](audiobuffer-class)\>

[dispatchEvent](../dart-html/eventtarget/dispatchevent)([Event](../dart-html/event-class)
event) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeEventListener](../dart-html/eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](../dart-html/eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[resume](baseaudiocontext/resume)() →
[Future](../dart-async/future-class)

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/BaseAudioContext-class.html>
:::
