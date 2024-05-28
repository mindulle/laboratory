[dart:html](../../dart-html/dart-html-library){._links-link}

getComputedStyle method
=======================

::: {.section .multi-line-signature}
[CssStyleDeclaration](../cssstyledeclaration-class) getComputedStyle(

1.  \[[String](../../dart-core/string-class)? pseudoElement\]

)
:::

The set of all CSS values applied to this element, including inherited
and default values.

The computedStyle contains values that are inherited from other sources,
such as parent elements or stylesheets. This differs from the
[style](style) property, which contains only the values specified
directly on this element.

PseudoElement can be values such as `::after`, `::before`, `::marker`,
`::line-marker`.

See also:

-   [Cascade and
    Inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Cascade_and_inheritance)
    from MDN.
-   [Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
CssStyleDeclaration getComputedStyle([String? pseudoElement]) {
  if (pseudoElement == null) {
    pseudoElement = '';
  }
  // TODO(jacobr): last param should be null, see b/5045788
  return window._getComputedStyle(this, pseudoElement);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/getComputedStyle.html>
:::
