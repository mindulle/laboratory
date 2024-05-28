[dart:html](../../dart-html/dart-html-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) operator ==(

1.  [Object](../../dart-core/object-class) other

)

::: {.features}
override
:::
:::

The equality operator.

The default behavior for all [Object](../../dart-core/object-class)s is
to return true if and only if this object and `other` are the same
object.

Override this method to specify a different equality relation on a
class. The overriding method must still be an equivalence relation. That
is, it must be:

-   Total: It must return a boolean for all arguments. It should never
    throw.

-   Reflexive: For all objects `o`, `o == o` must be true.

-   Symmetric: For all objects `o1` and `o2`, `o1 == o2` and `o2 == o1`
    must either both be true, or both be false.

-   Transitive: For all objects `o1`, `o2`, and `o3`, if `o1 == o2` and
    `o2 == o3` are true, then `o1 == o3` must be true.

The method should also be consistent over time, so whether two objects
are equal should only change if at least one of the objects was
modified.

If a subclass overrides the equality operator, it should override the
[hashCode](hashcode) method as well to maintain consistency.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(other) =>
    other is Rectangle &&
    left == other.left &&
    top == other.top &&
    right == other.right &&
    bottom == other.bottom;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssRect/operator_equals.html>
:::
