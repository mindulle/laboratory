[dart:html](../../dart-html/dart-html-library){._links-link}

drawImageScaledFromSource method
================================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'drawImage\')

</div>

void drawImageScaledFromSource(

1.  [CanvasImageSource](../canvasimagesource-class) source,
2.  [num](../../dart-core/num-class) sourceX,
3.  [num](../../dart-core/num-class) sourceY,
4.  [num](../../dart-core/num-class) sourceWidth,
5.  [num](../../dart-core/num-class) sourceHeight,
6.  [num](../../dart-core/num-class) destX,
7.  [num](../../dart-core/num-class) destY,
8.  [num](../../dart-core/num-class) destWidth,
9.  [num](../../dart-core/num-class) destHeight

)

::: {.features}
\@JSName(\'drawImage\')
:::
:::

Draws an image from a CanvasImageSource to an area of this canvas.

The image is a region of `source` that is `sourceWidth` wide and
`destHeight` tall with top left corner at (`sourceX`, `sourceY`). The
image will be drawn to this context with its top left corner at the
point (`destX`, `destY`) and will be scaled to be `destWidth` wide and
`destHeight` tall.

If the image is larger than canvas will allow, the image will be clipped
to fit the available space.

``` {.language-dart data-language="dart"}
VideoElement video = document.query('video');
video.width = 100;
video.height = 100;
// Take the middle 20x20 pixels from the video and stretch them.
ctx.drawImageScaledFromSource(video, 40, 40, 20, 20, 50, 50, 100, 100);

// Draw the top 100x20 pixels from the otherCanvas to this one.
CanvasElement otherCanvas = document.query('canvas');
ctx.drawImageScaledFromSource(otherCanvas, 0, 0, 100, 20, 0, 0, 100, 20);
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
void drawImageScaledFromSource(
    CanvasImageSource source,
    num sourceX,
    num sourceY,
    num sourceWidth,
    num sourceHeight,
    num destX,
    num destY,
    num destWidth,
    num destHeight) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/drawImageScaledFromSource.html>
:::
