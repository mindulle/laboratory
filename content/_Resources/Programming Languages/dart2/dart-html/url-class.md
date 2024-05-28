[dart:html](../dart-html/dart-html-library){._links-link}

Url class
=========

Annotations

:   -   \@Native(\"URL\")

Properties {#instance-properties}
----------

[hash](url/hash) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[host](url/host) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[hostname](url/hostname) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[href](url/href) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[origin](url/origin) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[password](url/password) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[pathname](url/pathname) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[port](url/port) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[protocol](url/protocol) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[search](url/search) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[searchParams](url/searchparams) →
[UrlSearchParams](urlsearchparams-class)?

::: {.features}
read-only
:::

[username](url/username) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](url/tostring)() → [String](../dart-core/string-class)

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

Static Methods
--------------

[createObjectUrl](url/createobjecturl)(dynamic
blob\_OR\_source\_OR\_stream) → [String](../dart-core/string-class)

[createObjectUrlFromBlob](url/createobjecturlfromblob)([Blob](blob-class)
blob) → [String](../dart-core/string-class)

[createObjectUrlFromSource](url/createobjecturlfromsource)([MediaSource](mediasource-class)
source) → [String](../dart-core/string-class)

[createObjectUrlFromStream](url/createobjecturlfromstream)([MediaStream](mediastream-class)
stream) → [String](../dart-core/string-class)

[revokeObjectUrl](url/revokeobjecturl)([String](../dart-core/string-class)
url) → void

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Url-class.html>
:::
