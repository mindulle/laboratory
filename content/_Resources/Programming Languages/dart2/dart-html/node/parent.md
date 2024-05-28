[dart:html](../../dart-html/dart-html-library){._links-link}

parent property
===============

::: {#getter .section .multi-line-signature}
[Element](../element-class)? parent

::: {.features}
\@JSName(\'parentElement\')
:::
:::

The parent element of this node.

Returns null if this node either does not have a parent or its parent is
not an element.

Other resources
---------------

-   [Node.parentElement](https://developer.mozilla.org/en-US/docs/Web/API/Node.parentElement)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('parentElement')

/**
 * The parent element of this node.
 *
 * Returns null if this node either does not have a parent or its parent is
 * not an element.
 *
 * ## Other resources
 *
 * * [Node.parentElement](https://developer.mozilla.org/en-US/docs/Web/API/Node.parentElement)
 *   from W3C.
 */

Element? get parent native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/parent.html>
:::
