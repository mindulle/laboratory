[dart:html](../dart-html/dart-html-library){._links-link}

FontFaceSet class
=================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   FontFaceSet

Annotations

:   -   \@Native(\"FontFaceSet\")

Properties {#instance-properties}
----------

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

[onLoading](fontfaceset/onloading) →
[Stream](../dart-async/stream-class)\<[FontFaceSetLoadEvent](fontfacesetloadevent-class)\>

::: {.features}
read-only
:::

[onLoadingDone](fontfaceset/onloadingdone) →
[Stream](../dart-async/stream-class)\<[FontFaceSetLoadEvent](fontfacesetloadevent-class)\>

::: {.features}
read-only
:::

[onLoadingError](fontfaceset/onloadingerror) →
[Stream](../dart-async/stream-class)\<[FontFaceSetLoadEvent](fontfacesetloadevent-class)\>

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[status](fontfaceset/status) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[add](fontfaceset/add)([FontFace](fontface-class) arg) →
[FontFaceSet](fontfaceset-class)?

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[check](fontfaceset/check)([String](../dart-core/string-class) font,
\[[String](../dart-core/string-class)? text\]) →
[bool](../dart-core/bool-class)

[clear](fontfaceset/clear)() → void

[delete](fontfaceset/delete)([FontFace](fontface-class) arg) →
[bool](../dart-core/bool-class)

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[forEach](fontfaceset/foreach)([FontFaceSetForEachCallback](fontfacesetforeachcallback)
callback, \[[Object](../dart-core/object-class)? thisArg\]) → void

[has](fontfaceset/has)([FontFace](fontface-class) arg) →
[bool](../dart-core/bool-class)

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

Constants
---------

[loadingDoneEvent](fontfaceset/loadingdoneevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[FontFaceSetLoadEvent](fontfacesetloadevent-class)\>

:   <div>

    `const EventStreamProvider<FontFaceSetLoadEvent>('loadingdone')`

    </div>

[loadingErrorEvent](fontfaceset/loadingerrorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[FontFaceSetLoadEvent](fontfacesetloadevent-class)\>

:   <div>

    `const EventStreamProvider<FontFaceSetLoadEvent>('loadingerror')`

    </div>

[loadingEvent](fontfaceset/loadingevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[FontFaceSetLoadEvent](fontfacesetloadevent-class)\>

:   <div>

    `const EventStreamProvider<FontFaceSetLoadEvent>('loading')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FontFaceSet-class.html>
:::
