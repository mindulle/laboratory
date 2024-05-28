[dart:html](../dart-html/dart-html-library){._links-link}

History class
=============

Implemented types

:   -   [HistoryBase](historybase-class)

Annotations

:   -   \@Native(\"History\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[length](history/length) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[scrollRestoration](history/scrollrestoration) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[state](history/state) → dynamic

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[back](history/back)() → void

::: {.features}
override
:::

[forward](history/forward)() → void

::: {.features}
override
:::

[go](history/go)(\[[int](../dart-core/int-class)? delta\]) → void

::: {.features}
override
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pushState](history/pushstate)(dynamic data,
[String](../dart-core/string-class) title,
[String](../dart-core/string-class)? url) → void

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

[replaceState](history/replacestate)(dynamic data,
[String](../dart-core/string-class) title,
[String](../dart-core/string-class)? url) → void

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI)
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

Static Properties
-----------------

[supportsState](history/supportsstate) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if the State APIs are supported on the current platform.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/History-class.html>
:::
