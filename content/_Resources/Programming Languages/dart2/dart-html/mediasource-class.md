[dart:html](../dart-html/dart-html-library){._links-link}

MediaSource class
=================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   MediaSource

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.IE, \'11\')
    -   \@Native(\"MediaSource\")

Constructors
------------

[MediaSource](mediasource/mediasource)()

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[activeSourceBuffers](mediasource/activesourcebuffers) →
[SourceBufferList](sourcebufferlist-class)?

::: {.features}
read-only
:::

[duration](mediasource/duration) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[readyState](mediasource/readystate) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sourceBuffers](mediasource/sourcebuffers) →
[SourceBufferList](sourcebufferlist-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[addSourceBuffer](mediasource/addsourcebuffer)([String](../dart-core/string-class)
type) → [SourceBuffer](sourcebuffer-class)

[clearLiveSeekableRange](mediasource/clearliveseekablerange)() → void

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[endOfStream](mediasource/endofstream)(\[[String](../dart-core/string-class)?
error\]) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[removeSourceBuffer](mediasource/removesourcebuffer)([SourceBuffer](sourcebuffer-class)
buffer) → void

[setLiveSeekableRange](mediasource/setliveseekablerange)([num](../dart-core/num-class)
start, [num](../dart-core/num-class) end) → void

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

Static Properties
-----------------

[supported](mediasource/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

Static Methods
--------------

[isTypeSupported](mediasource/istypesupported)([String](../dart-core/string-class)
type) → [bool](../dart-core/bool-class)

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaSource-class.html>
:::
