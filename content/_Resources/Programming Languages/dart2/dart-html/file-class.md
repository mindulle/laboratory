[dart:html](../dart-html/dart-html-library){._links-link}

File class
==========

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Blob](blob-class)
    -   File

Annotations

:   -   \@Native(\"File\")

Constructors
------------

[File](file/file)([List](../dart-core/list-class)\<[Object](../dart-core/object-class)\>
fileBits, [String](../dart-core/string-class) fileName,
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

[lastModified](file/lastmodified) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[lastModifiedDate](file/lastmodifieddate) →
[DateTime](../dart-core/datetime-class)

::: {.features}
read-only
:::

[name](file/name) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[relativePath](file/relativepath) → [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'webkitRelativePath\'),
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[size](blob/size) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[type](blob/type) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[slice](blob/slice)(\[[int](../dart-core/int-class)? start,
[int](../dart-core/int-class)? end, [String](../dart-core/string-class)?
contentType\]) → [Blob](blob-class)

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
<https://api.dart.dev/stable/2.18.5/dart-html/File-class.html>
:::
