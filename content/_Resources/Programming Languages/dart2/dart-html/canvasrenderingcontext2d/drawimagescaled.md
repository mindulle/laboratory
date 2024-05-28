[dart:html](../../dart-html/dart-html-library){._links-link}

drawImageScaled method
======================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'drawImage\')

</div>

void drawImageScaled(

1.  [CanvasImageSource](../canvasimagesource-class) source,
2.  [num](../../dart-core/num-class) destX,
3.  [num](../../dart-core/num-class) destY,
4.  [num](../../dart-core/num-class) destWidth,
5.  [num](../../dart-core/num-class) destHeight

)

::: {.features}
\@JSName(\'drawImage\')
:::
:::

Draws an image from a CanvasImageSource to an area of this canvas.

The image will be drawn to this context with its top left corner at the
point (`destX`, `destY`) and will be scaled to be `destWidth` wide and
`destHeight` tall.

If the image is larger than canvas will allow, the image will be clipped
to fit the available space.

``` {.language-dart data-language="dart"}
CanvasElement canvas = new CanvasElement(width: 600, height: 600);
CanvasRenderingContext2D ctx = canvas.context2D;
ImageElement img = document.query('img');
img.width = 100;
img.height = 100;

// Scale the image to 300x50 at the point (20, 20)
ctx.drawImageScaled(img, 20, 20, 300, 50);
```

See also:

-   [CanvasImageSource](../canvasimagesource-class) for more information
    on what data is retrieved from `source`.
-   [drawImage](http://www.whatwg.org/specs/web-apps/current-work/multipage/the-canvas-element.html#dom-context-2d-drawimage)
    from the WHATWG.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('drawImage')
void drawImageScaled(CanvasImageSource source, num destX, num destY,
    num destWidth, num destHeight) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/drawImageScaled.html>
:::
