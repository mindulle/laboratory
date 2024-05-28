[dart:html](../dart-html/dart-html-library){._links-link}

CssStyleSheet class
===================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StyleSheet](stylesheet-class)
    -   CssStyleSheet

Annotations

:   -   \@Native(\"CSSStyleSheet\")

Properties {#instance-properties}
----------

[cssRules](cssstylesheet/cssrules) →
[List](../dart-core/list-class)\<[CssRule](cssrule-class)\>

::: {.features}
\@Returns(\'\_CssRuleList\'), \@Creates(\'\_CssRuleList\'), read-only
:::

[disabled](stylesheet/disabled) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[href](stylesheet/href) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[media](stylesheet/media) → [MediaList](medialist-class)?

::: {.features}
read-only, inherited
:::

[ownerNode](stylesheet/ownernode) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

[ownerRule](cssstylesheet/ownerrule) → [CssRule](cssrule-class)?

::: {.features}
read-only
:::

[parentStyleSheet](stylesheet/parentstylesheet) →
[StyleSheet](stylesheet-class)?

::: {.features}
read-only, inherited
:::

[rules](cssstylesheet/rules) →
[List](../dart-core/list-class)\<[CssRule](cssrule-class)\>?

::: {.features}
\@Returns(\'\_CssRuleList\'), \@Creates(\'\_CssRuleList\'), read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[title](stylesheet/title) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[type](stylesheet/type) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

Methods {#instance-methods}
-------

[addRule](cssstylesheet/addrule)([String](../dart-core/string-class)?
selector, [String](../dart-core/string-class)? style,
\[[int](../dart-core/int-class)? index\]) →
[int](../dart-core/int-class)

[deleteRule](cssstylesheet/deleterule)([int](../dart-core/int-class)
index) → void

[insertRule](cssstylesheet/insertrule)([String](../dart-core/string-class)
rule, \[[int](../dart-core/int-class)? index\]) →
[int](../dart-core/int-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeRule](cssstylesheet/removerule)([int](../dart-core/int-class)?
index) → void

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
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleSheet-class.html>
:::
