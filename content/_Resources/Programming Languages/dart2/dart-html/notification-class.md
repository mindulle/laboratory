[dart:html](../dart-html/dart-html-library){._links-link}

Notification class
==================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   Notification

Annotations

:   -   \@Native(\"Notification\")

Constructors
------------

[Notification](notification/notification)([String](../dart-core/string-class)
title, {[String](../dart-core/string-class)? dir,
[String](../dart-core/string-class)? body,
[String](../dart-core/string-class)? lang,
[String](../dart-core/string-class)? tag,
[String](../dart-core/string-class)? icon})

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[actions](notification/actions) → [List](../dart-core/list-class)?

::: {.features}
read-only
:::

[badge](notification/badge) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[body](notification/body) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[data](notification/data) → [Object](../dart-core/object-class)?

::: {.features}
\@annotation\_Creates\_SerializedScriptValue,
\@annotation\_Returns\_SerializedScriptValue, read-only
:::

[dir](notification/dir) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[icon](notification/icon) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[image](notification/image) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[lang](notification/lang) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onClick](notification/onclick) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `click` events handled by this
[Notification](notification-class).

[onClose](notification/onclose) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `close` events handled by this
[Notification](notification-class).

[onError](notification/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this
[Notification](notification-class).

[onShow](notification/onshow) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `show` events handled by this
[Notification](notification-class).

[renotify](notification/renotify) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[requireInteraction](notification/requireinteraction) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[silent](notification/silent) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[tag](notification/tag) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[timestamp](notification/timestamp) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[title](notification/title) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[vibrate](notification/vibrate) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?

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

[close](notification/close)() → void

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

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

Static Properties
-----------------

[maxActions](notification/maxactions) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[permission](notification/permission) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[supported](notification/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

Static Methods
--------------

[requestPermission](notification/requestpermission)() →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
\@JSName(\'requestPermission\')
:::

Constants
---------

[clickEvent](notification/clickevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `click` events to event handlers
    that are not necessarily instances of
    [Notification](notification-class).
    <div>

    `const EventStreamProvider<Event>('click')`

    </div>

[closeEvent](notification/closeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `close` events to event handlers
    that are not necessarily instances of
    [Notification](notification-class).
    <div>

    `const EventStreamProvider<Event>('close')`

    </div>

[errorEvent](notification/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [Notification](notification-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[showEvent](notification/showevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `show` events to event handlers
    that are not necessarily instances of
    [Notification](notification-class).
    <div>

    `const EventStreamProvider<Event>('show')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Notification-class.html>
:::
