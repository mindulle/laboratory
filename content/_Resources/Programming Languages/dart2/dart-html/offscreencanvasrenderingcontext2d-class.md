[dart:html](../dart-html/dart-html-library){._links-link}

OffscreenCanvasRenderingContext2D class
=======================================

Annotations

:   -   \@Native(\"OffscreenCanvasRenderingContext2D\")

Properties {#instance-properties}
----------

[canvas](offscreencanvasrenderingcontext2d/canvas) →
[OffscreenCanvas](offscreencanvas-class)?

::: {.features}
read-only
:::

[direction](offscreencanvasrenderingcontext2d/direction) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[fillStyle](offscreencanvasrenderingcontext2d/fillstyle) ↔
[Object](../dart-core/object-class)?

::: {.features}
read / write
:::

[filter](offscreencanvasrenderingcontext2d/filter) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[font](offscreencanvasrenderingcontext2d/font) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[globalAlpha](offscreencanvasrenderingcontext2d/globalalpha) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[globalCompositeOperation](offscreencanvasrenderingcontext2d/globalcompositeoperation)
↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[imageSmoothingEnabled](offscreencanvasrenderingcontext2d/imagesmoothingenabled)
↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[imageSmoothingQuality](offscreencanvasrenderingcontext2d/imagesmoothingquality)
↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[lineCap](offscreencanvasrenderingcontext2d/linecap) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[lineDashOffset](offscreencanvasrenderingcontext2d/linedashoffset) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[lineJoin](offscreencanvasrenderingcontext2d/linejoin) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[lineWidth](offscreencanvasrenderingcontext2d/linewidth) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[miterLimit](offscreencanvasrenderingcontext2d/miterlimit) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[shadowBlur](offscreencanvasrenderingcontext2d/shadowblur) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[shadowColor](offscreencanvasrenderingcontext2d/shadowcolor) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[shadowOffsetX](offscreencanvasrenderingcontext2d/shadowoffsetx) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[shadowOffsetY](offscreencanvasrenderingcontext2d/shadowoffsety) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[strokeStyle](offscreencanvasrenderingcontext2d/strokestyle) ↔
[Object](../dart-core/object-class)?

::: {.features}
read / write
:::

[textAlign](offscreencanvasrenderingcontext2d/textalign) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[textBaseline](offscreencanvasrenderingcontext2d/textbaseline) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

Methods {#instance-methods}
-------

[arc](offscreencanvasrenderingcontext2d/arc)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class)
radius, [num](../dart-core/num-class) startAngle,
[num](../dart-core/num-class) endAngle, [bool](../dart-core/bool-class)?
anticlockwise) → void

[arcTo](offscreencanvasrenderingcontext2d/arcto)([num](../dart-core/num-class)
x1, [num](../dart-core/num-class) y1, [num](../dart-core/num-class) x2,
[num](../dart-core/num-class) y2, [num](../dart-core/num-class) radius)
→ void

[beginPath](offscreencanvasrenderingcontext2d/beginpath)() → void

[bezierCurveTo](offscreencanvasrenderingcontext2d/beziercurveto)([num](../dart-core/num-class)
cp1x, [num](../dart-core/num-class) cp1y, [num](../dart-core/num-class)
cp2x, [num](../dart-core/num-class) cp2y, [num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[clearRect](offscreencanvasrenderingcontext2d/clearrect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[clip](offscreencanvasrenderingcontext2d/clip)(\[[Path2D](path2d-class)?
path\]) → void

[closePath](offscreencanvasrenderingcontext2d/closepath)() → void

[commit](offscreencanvasrenderingcontext2d/commit)() →
[Future](../dart-async/future-class)

[createImageData](offscreencanvasrenderingcontext2d/createimagedata)(dynamic
data\_OR\_imagedata\_OR\_sw, \[[int](../dart-core/int-class)?
sh\_OR\_sw, dynamic imageDataColorSettings\_OR\_sh,
[Map](../dart-core/map-class)? imageDataColorSettings\]) →
[ImageData](imagedata-class)

[createLinearGradient](offscreencanvasrenderingcontext2d/createlineargradient)([num](../dart-core/num-class)
x0, [num](../dart-core/num-class) y0, [num](../dart-core/num-class) x1,
[num](../dart-core/num-class) y1) →
[CanvasGradient](canvasgradient-class)

[createPattern](offscreencanvasrenderingcontext2d/createpattern)(dynamic
image, [String](../dart-core/string-class) repetitionType) →
[CanvasPattern](canvaspattern-class)?

[createRadialGradient](offscreencanvasrenderingcontext2d/createradialgradient)([num](../dart-core/num-class)
x0, [num](../dart-core/num-class) y0, [num](../dart-core/num-class) r0,
[num](../dart-core/num-class) x1, [num](../dart-core/num-class) y1,
[num](../dart-core/num-class) r1) →
[CanvasGradient](canvasgradient-class)

[drawImage](offscreencanvasrenderingcontext2d/drawimage)(dynamic image,
[num](../dart-core/num-class) sx\_OR\_x, [num](../dart-core/num-class)
sy\_OR\_y, \[[num](../dart-core/num-class)? sw\_OR\_width,
[num](../dart-core/num-class)? height\_OR\_sh,
[num](../dart-core/num-class)? dx, [num](../dart-core/num-class)? dy,
[num](../dart-core/num-class)? dw, [num](../dart-core/num-class)? dh\])
→ void

[ellipse](offscreencanvasrenderingcontext2d/ellipse)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class)
radiusX, [num](../dart-core/num-class) radiusY,
[num](../dart-core/num-class) rotation, [num](../dart-core/num-class)
startAngle, [num](../dart-core/num-class) endAngle,
[bool](../dart-core/bool-class)? anticlockwise) → void

[fill](offscreencanvasrenderingcontext2d/fill)(\[dynamic
path\_OR\_winding, [String](../dart-core/string-class)? winding\]) →
void

[fillRect](offscreencanvasrenderingcontext2d/fillrect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[fillText](offscreencanvasrenderingcontext2d/filltext)([String](../dart-core/string-class)
text, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y,
\[[num](../dart-core/num-class)? maxWidth\]) → void

[getImageData](offscreencanvasrenderingcontext2d/getimagedata)([int](../dart-core/int-class)
sx, [int](../dart-core/int-class) sy, [int](../dart-core/int-class) sw,
[int](../dart-core/int-class) sh) → [ImageData](imagedata-class)

[getLineDash](offscreencanvasrenderingcontext2d/getlinedash)() →
[List](../dart-core/list-class)\<[num](../dart-core/num-class)\>

[isPointInPath](offscreencanvasrenderingcontext2d/ispointinpath)(dynamic
path\_OR\_x, [num](../dart-core/num-class) x\_OR\_y, \[dynamic
winding\_OR\_y, [String](../dart-core/string-class)? winding\]) →
[bool](../dart-core/bool-class)

[isPointInStroke](offscreencanvasrenderingcontext2d/ispointinstroke)(dynamic
path\_OR\_x, [num](../dart-core/num-class) x\_OR\_y,
\[[num](../dart-core/num-class)? y\]) → [bool](../dart-core/bool-class)

[lineTo](offscreencanvasrenderingcontext2d/lineto)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[measureText](offscreencanvasrenderingcontext2d/measuretext)([String](../dart-core/string-class)
text) → [TextMetrics](textmetrics-class)

[moveTo](offscreencanvasrenderingcontext2d/moveto)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[putImageData](offscreencanvasrenderingcontext2d/putimagedata)([ImageData](imagedata-class)
imagedata, [int](../dart-core/int-class) dx,
[int](../dart-core/int-class) dy, \[[int](../dart-core/int-class)?
dirtyX, [int](../dart-core/int-class)? dirtyY,
[int](../dart-core/int-class)? dirtyWidth,
[int](../dart-core/int-class)? dirtyHeight\]) → void

[quadraticCurveTo](offscreencanvasrenderingcontext2d/quadraticcurveto)([num](../dart-core/num-class)
cpx, [num](../dart-core/num-class) cpy, [num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → void

[rect](offscreencanvasrenderingcontext2d/rect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[resetTransform](offscreencanvasrenderingcontext2d/resettransform)() →
void

[restore](offscreencanvasrenderingcontext2d/restore)() → void

[rotate](offscreencanvasrenderingcontext2d/rotate)([num](../dart-core/num-class)
angle) → void

[save](offscreencanvasrenderingcontext2d/save)() → void

[scale](offscreencanvasrenderingcontext2d/scale)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[setLineDash](offscreencanvasrenderingcontext2d/setlinedash)([List](../dart-core/list-class)\<[num](../dart-core/num-class)\>
dash) → void

[setTransform](offscreencanvasrenderingcontext2d/settransform)([num](../dart-core/num-class)
a, [num](../dart-core/num-class) b, [num](../dart-core/num-class) c,
[num](../dart-core/num-class) d, [num](../dart-core/num-class) e,
[num](../dart-core/num-class) f) → void

[stroke](offscreencanvasrenderingcontext2d/stroke)(\[[Path2D](path2d-class)?
path\]) → void

[strokeRect](offscreencanvasrenderingcontext2d/strokerect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[strokeText](offscreencanvasrenderingcontext2d/stroketext)([String](../dart-core/string-class)
text, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y,
\[[num](../dart-core/num-class)? maxWidth\]) → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transform](offscreencanvasrenderingcontext2d/transform)([num](../dart-core/num-class)
a, [num](../dart-core/num-class) b, [num](../dart-core/num-class) c,
[num](../dart-core/num-class) d, [num](../dart-core/num-class) e,
[num](../dart-core/num-class) f) → void

[translate](offscreencanvasrenderingcontext2d/translate)([num](../dart-core/num-class)
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
<https://api.dart.dev/stable/2.18.5/dart-html/OffscreenCanvasRenderingContext2D-class.html>
:::
