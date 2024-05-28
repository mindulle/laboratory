[dart:html](../../dart-html/dart-html-library){._links-link}

width property
==============

::: {#getter .section .multi-line-signature}
[num](../../dart-core/num-class) width

::: {.features}
override
:::
:::

The width of this rectangle.

This is equivalent to the `width` function in jQuery and the calculated
`width` CSS value, converted to a dimensionless num in pixels. Unlike
[Element.getBoundingClientRect](../element/getboundingclientrect),
`width` will return the same numerical width if the element is hidden or
not.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
num get width;
```

::: {#setter .section .multi-line-signature}
void width=(dynamic newWidth)
:::

Set the current computed width in pixels of this element.

newWidth can be either a [num](../../dart-core/num-class) representing
the width in pixels or a [Dimension](../dimension-class) object. This is
equivalent to the `width` function in jQuery and the calculated `width`
CSS value, converted to a dimensionless num in pixels.

Note that only the content width can be set via this method.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set width(dynamic newWidth) {
  throw new UnsupportedError("Can only set width for content rect.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssRect/width.html>
:::
