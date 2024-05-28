[dart:html](../dart-html/dart-html-library){._links-link}

MutationObserver class
======================

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX)
    -   \@SupportedBrowser(SupportedBrowser.SAFARI)
    -   \@Native(\"MutationObserver,WebKitMutationObserver\")

Constructors
------------

[MutationObserver](mutationobserver/mutationobserver)([MutationCallback](mutationcallback)
callback)

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

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[disconnect](mutationobserver/disconnect)() → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[observe](mutationobserver/observe)([Node](node-class) target,
{[bool](../dart-core/bool-class)? childList,
[bool](../dart-core/bool-class)? attributes,
[bool](../dart-core/bool-class)? characterData,
[bool](../dart-core/bool-class)? subtree,
[bool](../dart-core/bool-class)? attributeOldValue,
[bool](../dart-core/bool-class)? characterDataOldValue,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?
attributeFilter}) → void

Observes the target for the specified changes.

[takeRecords](mutationobserver/takerecords)() →
[List](../dart-core/list-class)\<[MutationRecord](mutationrecord-class)\>

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

[supported](mutationobserver/supported) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks to see if the mutation observer API is supported on the current
platform.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MutationObserver-class.html>
:::
