[dart:html](../../dart-html/dart-html-library){._links-link}

drawImageToRect method
======================

::: {.section .multi-line-signature}
void drawImageToRect(

1.  [CanvasImageSource](../canvasimagesource-class) source,
2.  [Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
    destRect,
3.  {[Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>?
    sourceRect}

)
:::

Draws an image from a CanvasImageSource to an area of this canvas.

The image will be drawn to an area of this canvas defined by `destRect`.
`sourceRect` defines the region of the source image that is drawn. If
`sourceRect` is not provided, then the entire rectangular image from
`source` will be drawn to this context.

If the image is larger than canvas will allow, the image will be clipped
to fit the available space.

``` {.language-dart data-language="dart"}
CanvasElement canvas = new CanvasElement(width: 600, height: 600);
CanvasRenderingContext2D ctx = canvas.context2D;
ImageElement img = document.query('img');
img.width = 100;
img.height = 100;

// Scale the image to 20x20.
ctx.drawImageToRect(img, new Rectangle(50, 50, 20, 20));

VideoElement video = document.query('video');
video.width = 100;
video.height = 100;
// Take the middle 20x20 pixels from the video and stretch them.
ctx.drawImageToRect(video, new Rectangle(50, 50, 100, 100),
    sourceRect: new Rectangle(40, 40, 20, 20));

// Draw the top 100x20 pixels from the otherCanvas.
CanvasElement otherCanvas = document.query('canvas');
ctx.drawImageToRect(otherCanvas, new Rectangle(0, 0, 100, 20),
    sourceRect: new Rectangle(0, 0, 100, 20));
```

See also:

-   [CanvasImageSource](../canvasimagesource-class) for more information
    on what data is retrieved from `source`.
-   [drawImage](http://www.whatwg.org/specs/web-apps/current-work/multipage/the-canvas-element.html#dom-context-2d-drawimage)
    from the WHATWG.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void drawImageToRect(CanvasImageSource source, Rectangle destRect,
    {Rectangle? sourceRect}) {
  if (sourceRect == null) {
    drawImageScaled(
        source, destRect.left, destRect.top, destRect.width, destRect.height);
  } else {
    drawImageScaledFromSource(
        source,
        sourceRect.left,
        sourceRect.top,
        sourceRect.width,
        sourceRect.height,
        destRect.left,
        destRect.top,
        destRect.width,
        destRect.height);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/drawImageToRect.html>
:::
