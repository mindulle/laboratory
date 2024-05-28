[dart:html](../dart-html/dart-html-library){._links-link}

ServiceWorkerRegistration class
===============================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   ServiceWorkerRegistration

Annotations

:   -   \@Native(\"ServiceWorkerRegistration\")

Properties {#instance-properties}
----------

[active](serviceworkerregistration/active) →
[ServiceWorker](serviceworker-class)?

::: {.features}
read-only
:::

[backgroundFetch](serviceworkerregistration/backgroundfetch) →
[BackgroundFetchManager](backgroundfetchmanager-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[installing](serviceworkerregistration/installing) →
[ServiceWorker](serviceworker-class)?

::: {.features}
read-only
:::

[navigationPreload](serviceworkerregistration/navigationpreload) →
[NavigationPreloadManager](navigationpreloadmanager-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[paymentManager](serviceworkerregistration/paymentmanager) →
[PaymentManager](paymentmanager-class)?

::: {.features}
read-only
:::

[pushManager](serviceworkerregistration/pushmanager) →
[PushManager](pushmanager-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[scope](serviceworkerregistration/scope) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[sync](serviceworkerregistration/sync) →
[SyncManager](syncmanager-class)?

::: {.features}
read-only
:::

[waiting](serviceworkerregistration/waiting) →
[ServiceWorker](serviceworker-class)?

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

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getNotifications](serviceworkerregistration/getnotifications)(\[[Map](../dart-core/map-class)?
filter\]) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\>

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

[showNotification](serviceworkerregistration/shownotification)([String](../dart-core/string-class)
title, \[[Map](../dart-core/map-class)? options\]) →
[Future](../dart-async/future-class)

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[unregister](serviceworkerregistration/unregister)() →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

[update](serviceworkerregistration/update)() →
[Future](../dart-async/future-class)

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
<https://api.dart.dev/stable/2.18.5/dart-html/ServiceWorkerRegistration-class.html>
:::
