[dart:html](../dart-html/dart-html-library){._links-link}

XsltProcessor class
===================

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX)
    -   \@SupportedBrowser(SupportedBrowser.SAFARI)
    -   @[deprecated](../dart-core/deprecated-constant)
    -   \@Native(\"XSLTProcessor\")

Constructors
------------

[XsltProcessor](xsltprocessor/xsltprocessor)()

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

[clearParameters](xsltprocessor/clearparameters)() → void

[getParameter](xsltprocessor/getparameter)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) localName) →
[String](../dart-core/string-class)?

[importStylesheet](xsltprocessor/importstylesheet)([Node](node-class)
style) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeParameter](xsltprocessor/removeparameter)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) localName) → void

[reset](xsltprocessor/reset)() → void

[setParameter](xsltprocessor/setparameter)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) localName,
[String](../dart-core/string-class) value) → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transformToDocument](xsltprocessor/transformtodocument)([Node](node-class)
source) → [Document](document-class)?

[transformToFragment](xsltprocessor/transformtofragment)([Node](node-class)
source, [Document](document-class) output) →
[DocumentFragment](documentfragment-class)?

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

[supported](xsltprocessor/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/XsltProcessor-class.html>
:::
