[dart:html](../dart-html/dart-html-library){._links-link}

PaymentRequest class
====================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   PaymentRequest

Annotations

:   -   \@Native(\"PaymentRequest\")

Constructors
------------

[PaymentRequest](paymentrequest/paymentrequest)([List](../dart-core/list-class)\<[Map](../dart-core/map-class)\>
methodData, [Map](../dart-core/map-class) details,
\[[Map](../dart-core/map-class)? options\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](paymentrequest/id) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

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

[shippingAddress](paymentrequest/shippingaddress) →
[PaymentAddress](paymentaddress-class)?

::: {.features}
read-only
:::

[shippingOption](paymentrequest/shippingoption) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[shippingType](paymentrequest/shippingtype) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[abort](paymentrequest/abort)() → [Future](../dart-async/future-class)

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[canMakePayment](paymentrequest/canmakepayment)() →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

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

[show](paymentrequest/show)() →
[Future](../dart-async/future-class)\<[PaymentResponse](paymentresponse-class)\>

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
<https://api.dart.dev/stable/2.18.5/dart-html/PaymentRequest-class.html>
:::
