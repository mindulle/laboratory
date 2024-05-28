[dart:html](../dart-html/dart-html-library){._links-link}

CssMediaRule class
==================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [CssRule](cssrule-class)
    -   [CssGroupingRule](cssgroupingrule-class)
    -   [CssConditionRule](cssconditionrule-class)
    -   CssMediaRule

Annotations

:   -   \@Native(\"CSSMediaRule\")

Properties {#instance-properties}
----------

[conditionText](cssconditionrule/conditiontext) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[cssRules](cssgroupingrule/cssrules) →
[List](../dart-core/list-class)\<[CssRule](cssrule-class)\>?

::: {.features}
\@Returns(\'\_CssRuleList\'), \@Creates(\'\_CssRuleList\'), read-only,
inherited
:::

[cssText](cssrule/csstext) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[media](cssmediarule/media) → [MediaList](medialist-class)?

::: {.features}
read-only
:::

[parentRule](cssrule/parentrule) → [CssRule](cssrule-class)?

::: {.features}
read-only, inherited
:::

[parentStyleSheet](cssrule/parentstylesheet) →
[CssStyleSheet](cssstylesheet-class)?

::: {.features}
read-only, inherited
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[type](cssrule/type) → [int](../dart-core/int-class)?

::: {.features}
read-only, inherited
:::

Methods {#instance-methods}
-------

[deleteRule](cssgroupingrule/deleterule)([int](../dart-core/int-class)
index) → void

::: {.features}
inherited
:::

[insertRule](cssgroupingrule/insertrule)([String](../dart-core/string-class)
rule, [int](../dart-core/int-class) index) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

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
<https://api.dart.dev/stable/2.18.5/dart-html/CssMediaRule-class.html>
:::
