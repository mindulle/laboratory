[dart:html](../dart-html/dart-html-library){._links-link}

PaintRenderingContext2D class
=============================

Annotations

:   -   \@Native(\"PaintRenderingContext2D\")

Properties {#instance-properties}
----------

[currentTransform](paintrenderingcontext2d/currenttransform) ↔
[Matrix](../dart-svg/matrix-class)?

::: {.features}
read / write
:::

[fillStyle](paintrenderingcontext2d/fillstyle) ↔
[Object](../dart-core/object-class)?

::: {.features}
read / write
:::

[filter](paintrenderingcontext2d/filter) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[globalAlpha](paintrenderingcontext2d/globalalpha) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[globalCompositeOperation](paintrenderingcontext2d/globalcompositeoperation)
↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[imageSmoothingEnabled](paintrenderingcontext2d/imagesmoothingenabled) ↔
[bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[imageSmoothingQuality](paintrenderingcontext2d/imagesmoothingquality) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[lineCap](paintrenderingcontext2d/linecap) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[lineDashOffset](paintrenderingcontext2d/linedashoffset) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[lineJoin](paintrenderingcontext2d/linejoin) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[lineWidth](paintrenderingcontext2d/linewidth) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[miterLimit](paintrenderingcontext2d/miterlimit) ↔
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

[shadowBlur](paintrenderingcontext2d/shadowblur) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[shadowColor](paintrenderingcontext2d/shadowcolor) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[shadowOffsetX](paintrenderingcontext2d/shadowoffsetx) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[shadowOffsetY](paintrenderingcontext2d/shadowoffsety) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[strokeStyle](paintrenderingcontext2d/strokestyle) ↔
[Object](../dart-core/object-class)?

::: {.features}
read / write
:::

Methods {#instance-methods}
-------

[arc](paintrenderingcontext2d/arc)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y, [num](../dart-core/num-class) radius,
[num](../dart-core/num-class) startAngle, [num](../dart-core/num-class)
endAngle, [bool](../dart-core/bool-class)? anticlockwise) → void

[arcTo](paintrenderingcontext2d/arcto)([num](../dart-core/num-class) x1,
[num](../dart-core/num-class) y1, [num](../dart-core/num-class) x2,
[num](../dart-core/num-class) y2, [num](../dart-core/num-class) radius)
→ void

[beginPath](paintrenderingcontext2d/beginpath)() → void

[bezierCurveTo](paintrenderingcontext2d/beziercurveto)([num](../dart-core/num-class)
cp1x, [num](../dart-core/num-class) cp1y, [num](../dart-core/num-class)
cp2x, [num](../dart-core/num-class) cp2y, [num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[clearRect](paintrenderingcontext2d/clearrect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[clip](paintrenderingcontext2d/clip)(\[dynamic path\_OR\_winding,
[String](../dart-core/string-class)? winding\]) → void

[closePath](paintrenderingcontext2d/closepath)() → void

[createLinearGradient](paintrenderingcontext2d/createlineargradient)([num](../dart-core/num-class)
x0, [num](../dart-core/num-class) y0, [num](../dart-core/num-class) x1,
[num](../dart-core/num-class) y1) →
[CanvasGradient](canvasgradient-class)

[createPattern](paintrenderingcontext2d/createpattern)(dynamic image,
[String](../dart-core/string-class) repetitionType) →
[CanvasPattern](canvaspattern-class)?

[createRadialGradient](paintrenderingcontext2d/createradialgradient)([num](../dart-core/num-class)
x0, [num](../dart-core/num-class) y0, [num](../dart-core/num-class) r0,
[num](../dart-core/num-class) x1, [num](../dart-core/num-class) y1,
[num](../dart-core/num-class) r1) →
[CanvasGradient](canvasgradient-class)

[drawImage](paintrenderingcontext2d/drawimage)(dynamic image,
[num](../dart-core/num-class) sx\_OR\_x, [num](../dart-core/num-class)
sy\_OR\_y, \[[num](../dart-core/num-class)? sw\_OR\_width,
[num](../dart-core/num-class)? height\_OR\_sh,
[num](../dart-core/num-class)? dx, [num](../dart-core/num-class)? dy,
[num](../dart-core/num-class)? dw, [num](../dart-core/num-class)? dh\])
→ void

[ellipse](paintrenderingcontext2d/ellipse)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class)
radiusX, [num](../dart-core/num-class) radiusY,
[num](../dart-core/num-class) rotation, [num](../dart-core/num-class)
startAngle, [num](../dart-core/num-class) endAngle,
[bool](../dart-core/bool-class)? anticlockwise) → void

[fill](paintrenderingcontext2d/fill)(\[dynamic path\_OR\_winding,
[String](../dart-core/string-class)? winding\]) → void

[fillRect](paintrenderingcontext2d/fillrect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[getLineDash](paintrenderingcontext2d/getlinedash)() →
[List](../dart-core/list-class)\<[num](../dart-core/num-class)\>

[isPointInPath](paintrenderingcontext2d/ispointinpath)(dynamic
path\_OR\_x, [num](../dart-core/num-class) x\_OR\_y, \[dynamic
winding\_OR\_y, [String](../dart-core/string-class)? winding\]) →
[bool](../dart-core/bool-class)

[isPointInStroke](paintrenderingcontext2d/ispointinstroke)(dynamic
path\_OR\_x, [num](../dart-core/num-class) x\_OR\_y,
\[[num](../dart-core/num-class)? y\]) → [bool](../dart-core/bool-class)

[lineTo](paintrenderingcontext2d/lineto)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[moveTo](paintrenderingcontext2d/moveto)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[quadraticCurveTo](paintrenderingcontext2d/quadraticcurveto)([num](../dart-core/num-class)
cpx, [num](../dart-core/num-class) cpy, [num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → void

[rect](paintrenderingcontext2d/rect)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[resetTransform](paintrenderingcontext2d/resettransform)() → void

[restore](paintrenderingcontext2d/restore)() → void

[rotate](paintrenderingcontext2d/rotate)([num](../dart-core/num-class)
angle) → void

[save](paintrenderingcontext2d/save)() → void

[scale](paintrenderingcontext2d/scale)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → void

[setLineDash](paintrenderingcontext2d/setlinedash)([List](../dart-core/list-class)\<[num](../dart-core/num-class)\>
dash) → void

[setTransform](paintrenderingcontext2d/settransform)([num](../dart-core/num-class)
a, [num](../dart-core/num-class) b, [num](../dart-core/num-class) c,
[num](../dart-core/num-class) d, [num](../dart-core/num-class) e,
[num](../dart-core/num-class) f) → void

[stroke](paintrenderingcontext2d/stroke)(\[[Path2D](path2d-class)?
path\]) → void

[strokeRect](paintrenderingcontext2d/strokerect)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transform](paintrenderingcontext2d/transform)([num](../dart-core/num-class)
a, [num](../dart-core/num-class) b, [num](../dart-core/num-class) c,
[num](../dart-core/num-class) d, [num](../dart-core/num-class) e,
[num](../dart-core/num-class) f) → void

[translate](paintrenderingcontext2d/translate)([num](../dart-core/num-class)
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
<https://api.dart.dev/stable/2.18.5/dart-html/PaintRenderingContext2D-class.html>
:::
