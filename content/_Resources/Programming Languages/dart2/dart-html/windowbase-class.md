[dart:html](../dart-html/dart-html-library){._links-link}

WindowBase class
================

Top-level container for a browser tab or window.

In a web browser, a [WindowBase](windowbase-class) object represents any
browser window. This object contains the window\'s state and its
relation to other windows, such as which window opened this window.

**Note:** This class represents any window, while [Window](window-class)
is used to access the properties and content of the current window or
tab.

See also
--------

-   [Window](window-class)

Other resources
---------------

-   [DOM Window](https://developer.mozilla.org/en-US/docs/DOM/window)
    from MDN.
-   [Window](http://www.w3.org/TR/Window/) from the W3C.

Implemented types

:   -   [EventTarget](eventtarget-class)

Implementers

:   -   [Window](window-class)

Constructors
------------

[WindowBase](windowbase/windowbase)()

Properties {#instance-properties}
----------

[closed](windowbase/closed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

Indicates whether this window has been closed.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[history](windowbase/history) → [HistoryBase](historybase-class)

::: {.features}
read-only
:::

The current session history for this window.

[location](windowbase/location) → [LocationBase](locationbase-class)

::: {.features}
read-only
:::

The current location of this window.

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[opener](windowbase/opener) → [WindowBase](windowbase-class)?

::: {.features}
read-only
:::

A reference to the window that opened this one.

[parent](windowbase/parent) → [WindowBase](windowbase-class)?

::: {.features}
read-only
:::

A reference to the parent of this window.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[top](windowbase/top) → [WindowBase](windowbase-class)?

::: {.features}
read-only
:::

A reference to the topmost window in the window hierarchy.

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[close](windowbase/close)() → void

Closes the window.

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

[postMessage](windowbase/postmessage)(dynamic message,
[String](../dart-core/string-class) targetOrigin,
\[[List](../dart-core/list-class)\<[MessagePort](messageport-class)\>?
messagePorts\]) → void

Sends a cross-origin message.

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WindowBase-class.html>
:::
