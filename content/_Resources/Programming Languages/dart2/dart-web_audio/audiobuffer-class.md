[dart:web\_audio](../dart-web_audio/dart-web_audio-library){._links-link}

AudioBuffer class
=================

Annotations

:   -   \@Native(\"AudioBuffer\")

Constructors
------------

[AudioBuffer](audiobuffer/audiobuffer)([Map](../dart-core/map-class)
options)

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[duration](audiobuffer/duration) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[length](audiobuffer/length) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[numberOfChannels](audiobuffer/numberofchannels) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sampleRate](audiobuffer/samplerate) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[copyFromChannel](audiobuffer/copyfromchannel)([Float32List](../dart-typed_data/float32list-class)
destination, [int](../dart-core/int-class) channelNumber,
\[[int](../dart-core/int-class)? startInChannel\]) → void

[copyToChannel](audiobuffer/copytochannel)([Float32List](../dart-typed_data/float32list-class)
source, [int](../dart-core/int-class) channelNumber,
\[[int](../dart-core/int-class)? startInChannel\]) → void

[getChannelData](audiobuffer/getchanneldata)([int](../dart-core/int-class)
channelIndex) → [Float32List](../dart-typed_data/float32list-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

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
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioBuffer-class.html>
:::
