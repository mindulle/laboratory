[dart:html](../../dart-html/dart-html-library){._links-link}

height property
===============

::: {#getter .section .multi-line-signature}
[num](../../dart-core/num-class) height

::: {.features}
override
:::
:::

The height of this rectangle.

This is equivalent to the `height` function in jQuery and the calculated
`height` CSS value, converted to a dimensionless num in pixels. Unlike
[Element.getBoundingClientRect](../element/getboundingclientrect),
`height` will return the same numerical height if the element is hidden
or not.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
num get height;
```

::: {#setter .section .multi-line-signature}
void height=(dynamic newHeight)
:::

Set the height to `newHeight`.

newHeight can be either a [num](../../dart-core/num-class) representing
the height in pixels or a [Dimension](../dimension-class) object. Values
of newHeight that are less than zero are converted to effectively
setting the height to 0. This is equivalent to the `height` function in
jQuery and the calculated `height` CSS value, converted to a num in
pixels.

Note that only the content height can actually be set via this method.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set height(dynamic newHeight) {
  throw new UnsupportedError("Can only set height for content rect.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssRect/height.html>
:::
