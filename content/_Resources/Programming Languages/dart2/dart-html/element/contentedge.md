[dart:html](../../dart-html/dart-html-library){._links-link}

contentEdge property
====================

::: {#getter .section .multi-line-signature}
[CssRect](../cssrect-class) contentEdge
:::

Access this element\'s content position.

This returns a rectangle with the dimensions actually available for
content in this element, in pixels, regardless of this element\'s
box-sizing property. Unlike
[getBoundingClientRect](getboundingclientrect), the dimensions of this
rectangle will return the same numerical height if the element is hidden
or not.

*Important* *note*: use of this method *will* perform CSS calculations
that can trigger a browser reflow. Therefore, use of this property
*during* an animation frame is discouraged. See also: [Browser
Reflow](https://developers.google.com/speed/articles/reflow)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
CssRect get contentEdge => new _ContentCssRect(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/contentEdge.html>
:::
