[dart:html](../dart-html/dart-html-library){._links-link}

FormData class
==============

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX)
    -   \@SupportedBrowser(SupportedBrowser.IE, \'10\')
    -   \@SupportedBrowser(SupportedBrowser.SAFARI)
    -   \@Native(\"FormData\")

Constructors
------------

[FormData](formdata/formdata)(\[[FormElement](formelement-class)?
form\])

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

[append](formdata/append)([String](../dart-core/string-class) name,
[String](../dart-core/string-class) value) → void

[appendBlob](formdata/appendblob)([String](../dart-core/string-class)
name, [Blob](blob-class) value, \[[String](../dart-core/string-class)?
filename\]) → void

::: {.features}
\@JSName(\'append\')
:::

[delete](formdata/delete)([String](../dart-core/string-class) name) →
void

[get](formdata/get)([String](../dart-core/string-class) name) →
[Object](../dart-core/object-class)?

[getAll](formdata/getall)([String](../dart-core/string-class) name) →
[List](../dart-core/list-class)\<[Object](../dart-core/object-class)\>

[has](formdata/has)([String](../dart-core/string-class) name) →
[bool](../dart-core/bool-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[set](formdata/set)([String](../dart-core/string-class) name, dynamic
value, \[[String](../dart-core/string-class)? filename\]) → void

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

[supported](formdata/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FormData-class.html>
:::
