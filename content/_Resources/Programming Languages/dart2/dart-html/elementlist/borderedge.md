[dart:html](../../dart-html/dart-html-library){._links-link}

borderEdge property
===================

::: {#getter .section .multi-line-signature}
[CssRect](../cssrect-class) borderEdge
:::

Access dimensions and position of the first
[Element](../element-class)\'s content + padding + border box in this
list.

This returns a rectangle with the dimensions actually available for
content in this element, in pixels, regardless of this element\'s
box-sizing property. Unlike
[Element.getBoundingClientRect](../element/getboundingclientrect), the
dimensions of this rectangle will return the same numerical height if
the element is hidden or not. This can be used to retrieve jQuery\'s
`outerHeight` value for an element.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
CssRect get borderEdge;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ElementList/borderEdge.html>
:::
