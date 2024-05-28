[dart:html](../../dart-html/dart-html-library){._links-link}

drawImage method
================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'drawImage\')

</div>

void drawImage(

1.  [CanvasImageSource](../canvasimagesource-class) source,
2.  [num](../../dart-core/num-class) destX,
3.  [num](../../dart-core/num-class) destY

)

::: {.features}
\@JSName(\'drawImage\')
:::
:::

Draws an image from a CanvasImageSource to this canvas.

The entire image from `source` will be drawn to this context with its
top left corner at the point (`destX`, `destY`). If the image is larger
than canvas will allow, the image will be clipped to fit the available
space.

``` {.language-dart data-language="dart"}
CanvasElement canvas = new CanvasElement(width: 600, height: 600);
CanvasRenderingContext2D ctx = canvas.context2D;
ImageElement img = document.query('img');

ctx.drawImage(img, 100, 100);

VideoElement video = document.query('video');
ctx.drawImage(video, 0, 0);

CanvasElement otherCanvas = document.query('canvas');
otherCanvas.width = 100;
otherCanvas.height = 100;
ctx.drawImage(otherCanvas, 590, 590); // will get clipped
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
void drawImage(CanvasImageSource source, num destX, num destY) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/drawImage.html>
:::
