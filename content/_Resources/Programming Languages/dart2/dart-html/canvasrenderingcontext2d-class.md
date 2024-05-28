[dart:html](../dart-html/dart-html-library){._links-link}

CanvasRenderingContext2D class
==============================

Implemented types

:   -   [CanvasRenderingContext](canvasrenderingcontext-class)

Annotations

:   -   \@Native(\"CanvasRenderingContext2D\")

Properties {#instance-properties}
----------

[backingStorePixelRatio](canvasrenderingcontext2d/backingstorepixelratio){.deprecated}
→ [double](../dart-core/double-class)

::: {.features}
read-only
:::

Deprecated always returns 1.0

[canvas](canvasrenderingcontext2d/canvas) →
[CanvasElement](canvaselement-class)

::: {.features}
read-only, override
:::

[currentTransform](canvasrenderingcontext2d/currenttransform) ↔
[Matrix](../dart-svg/matrix-class)?

::: {.features}
read / write
:::

[direction](canvasrenderingcontext2d/direction) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[fillStyle](canvasrenderingcontext2d/fillstyle) ↔
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'String\|CanvasGradient\|CanvasPattern\'),
\@Returns(\'String\|CanvasGradient\|CanvasPattern\'), read / write
:::

[filter](canvasrenderingcontext2d/filter) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[font](canvasrenderingcontext2d/font) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

[globalAlpha](canvasrenderingcontext2d/globalalpha) ↔
[num](../dart-core/num-class)

::: {.features}
read / write
:::

[globalCompositeOperation](canvasrenderingcontext2d/globalcompositeoperation)
↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[imageSmoothingEnabled](canvasrenderingcontext2d/imagesmoothingenabled)
↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

Whether images and patterns on this canvas will be smoothed when this
canvas is scaled.

[imageSmoothingQuality](canvasrenderingcontext2d/imagesmoothingquality)
↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[lineCap](canvasrenderingcontext2d/linecap) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

[lineDashOffset](canvasrenderingcontext2d/linedashoffset) ↔
[num](../dart-core/num-class)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI),
\@SupportedBrowser(SupportedBrowser.IE, \'11\'), \@Unstable(),
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI),
\@SupportedBrowser(SupportedBrowser.IE, \'11\'), \@Unstable(), read /
write
:::

[lineJoin](canvasrenderingcontext2d/linejoin) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

[lineWidth](canvasrenderingcontext2d/linewidth) ↔
[num](../dart-core/num-class)

::: {.features}
read / write
:::

[miterLimit](canvasrenderingcontext2d/miterlimit) ↔
[num](../dart-core/num-class)

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[shadowBlur](canvasrenderingcontext2d/shadowblur) ↔
[num](../dart-core/num-class)

::: {.features}
read / write
:::

[shadowColor](canvasrenderingcontext2d/shadowcolor) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

[shadowOffsetX](canvasrenderingcontext2d/shadowoffsetx) ↔
[num](../dart-core/num-class)

::: {.features}
read / write
:::

[shadowOffsetY](canvasrenderingcontext2d/shadowoffsety) ↔
[num](../dart-core/num-class)

::: {.features}
read / write
:::

[strokeStyle](canvasrenderingcontext2d/strokestyle) ↔
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'String\|CanvasGradient\|CanvasPattern\'),
\@Returns(\'String\|CanvasGradient\|CanvasPattern\'), read / write
:::

[textAlign](canvasrenderingcontext2d/textalign) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

[textBaseline](canvasrenderingcontext2d/textbaseline) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

Methods {#instance-methods}
-------

[addHitRegion](canvasrenderingcontext2d/addhitregion)(\[[Map](../dart-core/map-class)?
options\]) → void

[arc](canvasrenderingcontext2d/arc)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y, [num](../dart-core/num-class) radius,
[num](../dart-core/num-class) startAngle, [num](../dart-core/num-class)
endAngle, \[[bool](../dart-core/bool-class) anticlockwise = false\]) →
void

[arcTo](canvasrenderingcontext2d/arcto)([num](../dart-core/num-class)
x1, [num](../dart-core/num-class) y1, [num](../dart-core/num-class) x2,
[num](../dart-core/num-class) y2, [num](../dart-core/num-class) radius)
→ void

[beginPath](canvasrenderingcontext2d/beginpath)() → void

[bezierCurveTo](canvasrenderingcontext2d/beziercurveto)([num](../dart-core/num-class)
cp1x, [num](../dart-core/num-class) cp1y, [num](../dart-core/num-class)
cp2x, [num](../dart-core/num-class) cp2y, [num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[clearHitRegions](canvasrenderingcontext2d/clearhitregions)() → void

[clearRect](canvasrenderingcontext2d/clearrect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[clip](canvasrenderingcontext2d/clip)(\[dynamic path\_OR\_winding,
[String](../dart-core/string-class)? winding\]) → void

[closePath](canvasrenderingcontext2d/closepath)() → void

[createImageData](canvasrenderingcontext2d/createimagedata)(dynamic
data\_OR\_imagedata\_OR\_sw, \[[int](../dart-core/int-class)?
sh\_OR\_sw, dynamic imageDataColorSettings\_OR\_sh,
[Map](../dart-core/map-class)? imageDataColorSettings\]) →
[ImageData](imagedata-class)

::: {.features}
\@Creates(\'ImageData\|=Object\')
:::

[createImageDataFromImageData](canvasrenderingcontext2d/createimagedatafromimagedata)([ImageData](imagedata-class)
imagedata) → [ImageData](imagedata-class)

[createLinearGradient](canvasrenderingcontext2d/createlineargradient)([num](../dart-core/num-class)
x0, [num](../dart-core/num-class) y0, [num](../dart-core/num-class) x1,
[num](../dart-core/num-class) y1) →
[CanvasGradient](canvasgradient-class)

[createPattern](canvasrenderingcontext2d/createpattern)([Object](../dart-core/object-class)
image, [String](../dart-core/string-class) repetitionType) →
[CanvasPattern](canvaspattern-class)?

[createPatternFromImage](canvasrenderingcontext2d/createpatternfromimage)([ImageElement](imageelement-class)
image, [String](../dart-core/string-class) repetitionType) →
[CanvasPattern](canvaspattern-class)

[createRadialGradient](canvasrenderingcontext2d/createradialgradient)([num](../dart-core/num-class)
x0, [num](../dart-core/num-class) y0, [num](../dart-core/num-class) r0,
[num](../dart-core/num-class) x1, [num](../dart-core/num-class) y1,
[num](../dart-core/num-class) r1) →
[CanvasGradient](canvasgradient-class)

[drawFocusIfNeeded](canvasrenderingcontext2d/drawfocusifneeded)(dynamic
element\_OR\_path, \[[Element](element-class)? element\]) → void

[drawImage](canvasrenderingcontext2d/drawimage)([CanvasImageSource](canvasimagesource-class)
source, [num](../dart-core/num-class) destX,
[num](../dart-core/num-class) destY) → void

::: {.features}
\@JSName(\'drawImage\')
:::

Draws an image from a CanvasImageSource to this canvas.

[drawImageScaled](canvasrenderingcontext2d/drawimagescaled)([CanvasImageSource](canvasimagesource-class)
source, [num](../dart-core/num-class) destX,
[num](../dart-core/num-class) destY, [num](../dart-core/num-class)
destWidth, [num](../dart-core/num-class) destHeight) → void

::: {.features}
\@JSName(\'drawImage\')
:::

Draws an image from a CanvasImageSource to an area of this canvas.

[drawImageScaledFromSource](canvasrenderingcontext2d/drawimagescaledfromsource)([CanvasImageSource](canvasimagesource-class)
source, [num](../dart-core/num-class) sourceX,
[num](../dart-core/num-class) sourceY, [num](../dart-core/num-class)
sourceWidth, [num](../dart-core/num-class) sourceHeight,
[num](../dart-core/num-class) destX, [num](../dart-core/num-class)
destY, [num](../dart-core/num-class) destWidth,
[num](../dart-core/num-class) destHeight) → void

::: {.features}
\@JSName(\'drawImage\')
:::

Draws an image from a CanvasImageSource to an area of this canvas.

[drawImageToRect](canvasrenderingcontext2d/drawimagetorect)([CanvasImageSource](canvasimagesource-class)
source,
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
destRect,
{[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>?
sourceRect}) → void

Draws an image from a CanvasImageSource to an area of this canvas.

[ellipse](canvasrenderingcontext2d/ellipse)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class)
radiusX, [num](../dart-core/num-class) radiusY,
[num](../dart-core/num-class) rotation, [num](../dart-core/num-class)
startAngle, [num](../dart-core/num-class) endAngle,
[bool](../dart-core/bool-class)? anticlockwise) → void

[fill](canvasrenderingcontext2d/fill)(\[dynamic path\_OR\_winding,
[String](../dart-core/string-class)? winding\]) → void

[fillRect](canvasrenderingcontext2d/fillrect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[fillText](canvasrenderingcontext2d/filltext)([String](../dart-core/string-class)
text, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y,
\[[num](../dart-core/num-class)? maxWidth\]) → void

Draws text to the canvas.

[getContextAttributes](canvasrenderingcontext2d/getcontextattributes)()
→ [Map](../dart-core/map-class)

[getImageData](canvasrenderingcontext2d/getimagedata)([int](../dart-core/int-class)
sx, [int](../dart-core/int-class) sy, [int](../dart-core/int-class) sw,
[int](../dart-core/int-class) sh) → [ImageData](imagedata-class)

::: {.features}
\@Creates(\'ImageData\|=Object\')
:::

[getLineDash](canvasrenderingcontext2d/getlinedash)() →
[List](../dart-core/list-class)\<[num](../dart-core/num-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI),
\@SupportedBrowser(SupportedBrowser.IE, \'11\'), \@Unstable()
:::

[isContextLost](canvasrenderingcontext2d/iscontextlost)() →
[bool](../dart-core/bool-class)

[isPointInPath](canvasrenderingcontext2d/ispointinpath)(dynamic
path\_OR\_x, [num](../dart-core/num-class) x\_OR\_y, \[dynamic
winding\_OR\_y, [String](../dart-core/string-class)? winding\]) →
[bool](../dart-core/bool-class)

[isPointInStroke](canvasrenderingcontext2d/ispointinstroke)(dynamic
path\_OR\_x, [num](../dart-core/num-class) x\_OR\_y,
\[[num](../dart-core/num-class)? y\]) → [bool](../dart-core/bool-class)

[lineTo](canvasrenderingcontext2d/lineto)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[measureText](canvasrenderingcontext2d/measuretext)([String](../dart-core/string-class)
text) → [TextMetrics](textmetrics-class)

[moveTo](canvasrenderingcontext2d/moveto)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[putImageData](canvasrenderingcontext2d/putimagedata)([ImageData](imagedata-class)
imagedata, [int](../dart-core/int-class) dx,
[int](../dart-core/int-class) dy, \[[int](../dart-core/int-class)?
dirtyX, [int](../dart-core/int-class)? dirtyY,
[int](../dart-core/int-class)? dirtyWidth,
[int](../dart-core/int-class)? dirtyHeight\]) → void

[quadraticCurveTo](canvasrenderingcontext2d/quadraticcurveto)([num](../dart-core/num-class)
cpx, [num](../dart-core/num-class) cpy, [num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → void

[rect](canvasrenderingcontext2d/rect)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[removeHitRegion](canvasrenderingcontext2d/removehitregion)([String](../dart-core/string-class)
id) → void

[resetTransform](canvasrenderingcontext2d/resettransform)() → void

[restore](canvasrenderingcontext2d/restore)() → void

[rotate](canvasrenderingcontext2d/rotate)([num](../dart-core/num-class)
angle) → void

[save](canvasrenderingcontext2d/save)() → void

[scale](canvasrenderingcontext2d/scale)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → void

[scrollPathIntoView](canvasrenderingcontext2d/scrollpathintoview)(\[[Path2D](path2d-class)?
path\]) → void

[setFillColorHsl](canvasrenderingcontext2d/setfillcolorhsl)([int](../dart-core/int-class)
h, [num](../dart-core/num-class) s, [num](../dart-core/num-class) l,
\[[num](../dart-core/num-class) a = 1\]) → void

Sets the color used inside shapes. `h` is in degrees, 0-360. `s`, `l`
are in percent, 0-100. `a` is 0-1.

[setFillColorRgb](canvasrenderingcontext2d/setfillcolorrgb)([int](../dart-core/int-class)
r, [int](../dart-core/int-class) g, [int](../dart-core/int-class) b,
\[[num](../dart-core/num-class) a = 1\]) → void

Sets the color used inside shapes. `r`, `g`, `b` are 0-255, `a` is 0-1.

[setLineDash](canvasrenderingcontext2d/setlinedash)([List](../dart-core/list-class)\<[num](../dart-core/num-class)\>
dash) → void

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI),
\@SupportedBrowser(SupportedBrowser.IE, \'11\'), \@Unstable()
:::

[setStrokeColorHsl](canvasrenderingcontext2d/setstrokecolorhsl)([int](../dart-core/int-class)
h, [num](../dart-core/num-class) s, [num](../dart-core/num-class) l,
\[[num](../dart-core/num-class) a = 1\]) → void

Sets the color used for stroking shapes. `h` is in degrees, 0-360. `s`,
`l` are in percent, 0-100. `a` is 0-1.

[setStrokeColorRgb](canvasrenderingcontext2d/setstrokecolorrgb)([int](../dart-core/int-class)
r, [int](../dart-core/int-class) g, [int](../dart-core/int-class) b,
\[[num](../dart-core/num-class) a = 1\]) → void

Sets the color used for stroking shapes. `r`, `g`, `b` are 0-255, `a` is
0-1.

[setTransform](canvasrenderingcontext2d/settransform)([num](../dart-core/num-class)
a, [num](../dart-core/num-class) b, [num](../dart-core/num-class) c,
[num](../dart-core/num-class) d, [num](../dart-core/num-class) e,
[num](../dart-core/num-class) f) → void

[stroke](canvasrenderingcontext2d/stroke)(\[[Path2D](path2d-class)?
path\]) → void

[strokeRect](canvasrenderingcontext2d/strokerect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[strokeText](canvasrenderingcontext2d/stroketext)([String](../dart-core/string-class)
text, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y,
\[[num](../dart-core/num-class)? maxWidth\]) → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transform](canvasrenderingcontext2d/transform)([num](../dart-core/num-class)
a, [num](../dart-core/num-class) b, [num](../dart-core/num-class) c,
[num](../dart-core/num-class) d, [num](../dart-core/num-class) e,
[num](../dart-core/num-class) f) → void

[translate](canvasrenderingcontext2d/translate)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D-class.html>
:::
