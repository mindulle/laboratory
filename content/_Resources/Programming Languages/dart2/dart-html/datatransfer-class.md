[dart:html](../dart-html/dart-html-library){._links-link}

DataTransfer class
==================

Annotations

:   -   \@Native(\"DataTransfer\")

Constructors
------------

[DataTransfer](datatransfer/datatransfer)()

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[dropEffect](datatransfer/dropeffect) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[effectAllowed](datatransfer/effectallowed) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[files](datatransfer/files) →
[List](../dart-core/list-class)\<[File](file-class)\>?

::: {.features}
\@Returns(\'FileList\'), \@Creates(\'FileList\'), read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[items](datatransfer/items) →
[DataTransferItemList](datatransferitemlist-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[types](datatransfer/types) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[clearData](datatransfer/cleardata)(\[[String](../dart-core/string-class)?
format\]) → void

[getData](datatransfer/getdata)([String](../dart-core/string-class)
format) → [String](../dart-core/string-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setData](datatransfer/setdata)([String](../dart-core/string-class)
format, [String](../dart-core/string-class) data) → void

[setDragImage](datatransfer/setdragimage)([Element](element-class)
image, [int](../dart-core/int-class) x, [int](../dart-core/int-class) y)
→ void

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
<https://api.dart.dev/stable/2.18.5/dart-html/DataTransfer-class.html>
:::
