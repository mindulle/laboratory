[dart:html](../dart-html/dart-html-library){._links-link}

SecurityPolicyViolationEvent class
==================================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Event](event-class)
    -   SecurityPolicyViolationEvent

Annotations

:   -   \@Native(\"SecurityPolicyViolationEvent\")

Constructors
------------

[SecurityPolicyViolationEvent](securitypolicyviolationevent/securitypolicyviolationevent)([String](../dart-core/string-class)
type, \[[Map](../dart-core/map-class)? eventInitDict\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[blockedUri](securitypolicyviolationevent/blockeduri) →
[String](../dart-core/string-class)?

::: {.features}
\@JSName(\'blockedURI\'), read-only
:::

[bubbles](event/bubbles) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[cancelable](event/cancelable) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[columnNumber](securitypolicyviolationevent/columnnumber) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[composed](event/composed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[currentTarget](event/currenttarget) → [EventTarget](eventtarget-class)?

::: {.features}
read-only, inherited
:::

[defaultPrevented](event/defaultprevented) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[disposition](securitypolicyviolationevent/disposition) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[documentUri](securitypolicyviolationevent/documenturi) →
[String](../dart-core/string-class)?

::: {.features}
\@JSName(\'documentURI\'), read-only
:::

[effectiveDirective](securitypolicyviolationevent/effectivedirective) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[eventPhase](event/eventphase) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isTrusted](event/istrusted) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[lineNumber](securitypolicyviolationevent/linenumber) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[matchingTarget](event/matchingtarget) → [Element](element-class)

::: {.features}
read-only, inherited
:::

A pointer to the element whose CSS selector matched within which an
event was fired. If this Event was not associated with any Event
delegation, accessing this value will throw an
[UnsupportedError](../dart-core/unsupportederror-class).

[originalPolicy](securitypolicyviolationevent/originalpolicy) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[path](event/path) →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
read-only, inherited
:::

[referrer](securitypolicyviolationevent/referrer) →
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

[sample](securitypolicyviolationevent/sample) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[sourceFile](securitypolicyviolationevent/sourcefile) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[statusCode](securitypolicyviolationevent/statuscode) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[target](event/target) → [EventTarget](eventtarget-class)?

::: {.features}
read-only, inherited
:::

[timeStamp](event/timestamp) → [num](../dart-core/num-class)?

::: {.features}
read-only, inherited
:::

[type](event/type) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

[violatedDirective](securitypolicyviolationevent/violateddirective) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[composedPath](event/composedpath)() →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[preventDefault](event/preventdefault)() → void

::: {.features}
inherited
:::

[stopImmediatePropagation](event/stopimmediatepropagation)() → void

::: {.features}
inherited
:::

[stopPropagation](event/stoppropagation)() → void

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
<https://api.dart.dev/stable/2.18.5/dart-html/SecurityPolicyViolationEvent-class.html>
:::
