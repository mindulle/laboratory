[dart:web\_gl](../dart-web_gl/dart-web_gl-library){._links-link}

RenderingContext class
======================

Implemented types

:   -   [CanvasRenderingContext](../dart-html/canvasrenderingcontext-class)

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX)
    -   \@Unstable()
    -   \@Native(\"WebGLRenderingContext\")

Properties {#instance-properties}
----------

[canvas](renderingcontext/canvas) →
[CanvasElement](../dart-html/canvaselement-class)

::: {.features}
read-only, override
:::

[drawingBufferHeight](renderingcontext/drawingbufferheight) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[drawingBufferWidth](renderingcontext/drawingbufferwidth) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[activeTexture](renderingcontext/activetexture)([int](../dart-core/int-class)
texture) → void

[attachShader](renderingcontext/attachshader)([Program](program-class)
program, [Shader](shader-class) shader) → void

[bindAttribLocation](renderingcontext/bindattriblocation)([Program](program-class)
program, [int](../dart-core/int-class) index,
[String](../dart-core/string-class) name) → void

[bindBuffer](renderingcontext/bindbuffer)([int](../dart-core/int-class)
target, [Buffer](buffer-class)? buffer) → void

[bindFramebuffer](renderingcontext/bindframebuffer)([int](../dart-core/int-class)
target, [Framebuffer](framebuffer-class)? framebuffer) → void

[bindRenderbuffer](renderingcontext/bindrenderbuffer)([int](../dart-core/int-class)
target, [Renderbuffer](renderbuffer-class)? renderbuffer) → void

[bindTexture](renderingcontext/bindtexture)([int](../dart-core/int-class)
target, [Texture](texture-class)? texture) → void

[blendColor](renderingcontext/blendcolor)([num](../dart-core/num-class)
red, [num](../dart-core/num-class) green, [num](../dart-core/num-class)
blue, [num](../dart-core/num-class) alpha) → void

[blendEquation](renderingcontext/blendequation)([int](../dart-core/int-class)
mode) → void

[blendEquationSeparate](renderingcontext/blendequationseparate)([int](../dart-core/int-class)
modeRGB, [int](../dart-core/int-class) modeAlpha) → void

[blendFunc](renderingcontext/blendfunc)([int](../dart-core/int-class)
sfactor, [int](../dart-core/int-class) dfactor) → void

[blendFuncSeparate](renderingcontext/blendfuncseparate)([int](../dart-core/int-class)
srcRGB, [int](../dart-core/int-class) dstRGB,
[int](../dart-core/int-class) srcAlpha, [int](../dart-core/int-class)
dstAlpha) → void

[bufferData](renderingcontext/bufferdata)([int](../dart-core/int-class)
target, dynamic data\_OR\_size, [int](../dart-core/int-class) usage) →
void

[bufferDataTyped](renderingcontext/bufferdatatyped){.deprecated}([int](../dart-core/int-class)
target, [TypedData](../dart-typed_data/typeddata-class) data,
[int](../dart-core/int-class) usage) → void

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"Use bufferData\")
:::

Set the bufferData to `data`.

[bufferSubData](renderingcontext/buffersubdata)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) offset, dynamic data) → void

[bufferSubDataTyped](renderingcontext/buffersubdatatyped){.deprecated}([int](../dart-core/int-class)
target, [int](../dart-core/int-class) offset,
[TypedData](../dart-typed_data/typeddata-class) data) → void

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"Use bufferSubData\")
:::

Set the bufferSubData to `data`.

[checkFramebufferStatus](renderingcontext/checkframebufferstatus)([int](../dart-core/int-class)
target) → [int](../dart-core/int-class)

[clear](renderingcontext/clear)([int](../dart-core/int-class) mask) →
void

[clearColor](renderingcontext/clearcolor)([num](../dart-core/num-class)
red, [num](../dart-core/num-class) green, [num](../dart-core/num-class)
blue, [num](../dart-core/num-class) alpha) → void

[clearDepth](renderingcontext/cleardepth)([num](../dart-core/num-class)
depth) → void

[clearStencil](renderingcontext/clearstencil)([int](../dart-core/int-class)
s) → void

[colorMask](renderingcontext/colormask)([bool](../dart-core/bool-class)
red, [bool](../dart-core/bool-class) green,
[bool](../dart-core/bool-class) blue, [bool](../dart-core/bool-class)
alpha) → void

[commit](renderingcontext/commit)() →
[Future](../dart-async/future-class)

[compileShader](renderingcontext/compileshader)([Shader](shader-class)
shader) → void

[compressedTexImage2D](renderingcontext/compressedteximage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) border,
[TypedData](../dart-typed_data/typeddata-class) data) → void

[compressedTexSubImage2D](renderingcontext/compressedtexsubimage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
format, [TypedData](../dart-typed_data/typeddata-class) data) → void

[copyTexImage2D](renderingcontext/copyteximage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) x, [int](../dart-core/int-class) y,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) border) → void

[copyTexSubImage2D](renderingcontext/copytexsubimage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) x, [int](../dart-core/int-class)
y, [int](../dart-core/int-class) width, [int](../dart-core/int-class)
height) → void

[createBuffer](renderingcontext/createbuffer)() → [Buffer](buffer-class)

[createFramebuffer](renderingcontext/createframebuffer)() →
[Framebuffer](framebuffer-class)

[createProgram](renderingcontext/createprogram)() →
[Program](program-class)

[createRenderbuffer](renderingcontext/createrenderbuffer)() →
[Renderbuffer](renderbuffer-class)

[createShader](renderingcontext/createshader)([int](../dart-core/int-class)
type) → [Shader](shader-class)

[createTexture](renderingcontext/createtexture)() →
[Texture](texture-class)

[cullFace](renderingcontext/cullface)([int](../dart-core/int-class)
mode) → void

[deleteBuffer](renderingcontext/deletebuffer)([Buffer](buffer-class)?
buffer) → void

[deleteFramebuffer](renderingcontext/deleteframebuffer)([Framebuffer](framebuffer-class)?
framebuffer) → void

[deleteProgram](renderingcontext/deleteprogram)([Program](program-class)?
program) → void

[deleteRenderbuffer](renderingcontext/deleterenderbuffer)([Renderbuffer](renderbuffer-class)?
renderbuffer) → void

[deleteShader](renderingcontext/deleteshader)([Shader](shader-class)?
shader) → void

[deleteTexture](renderingcontext/deletetexture)([Texture](texture-class)?
texture) → void

[depthFunc](renderingcontext/depthfunc)([int](../dart-core/int-class)
func) → void

[depthMask](renderingcontext/depthmask)([bool](../dart-core/bool-class)
flag) → void

[depthRange](renderingcontext/depthrange)([num](../dart-core/num-class)
zNear, [num](../dart-core/num-class) zFar) → void

[detachShader](renderingcontext/detachshader)([Program](program-class)
program, [Shader](shader-class) shader) → void

[disable](renderingcontext/disable)([int](../dart-core/int-class) cap) →
void

[disableVertexAttribArray](renderingcontext/disablevertexattribarray)([int](../dart-core/int-class)
index) → void

[drawArrays](renderingcontext/drawarrays)([int](../dart-core/int-class)
mode, [int](../dart-core/int-class) first, [int](../dart-core/int-class)
count) → void

[drawElements](renderingcontext/drawelements)([int](../dart-core/int-class)
mode, [int](../dart-core/int-class) count, [int](../dart-core/int-class)
type, [int](../dart-core/int-class) offset) → void

[enable](renderingcontext/enable)([int](../dart-core/int-class) cap) →
void

[enableVertexAttribArray](renderingcontext/enablevertexattribarray)([int](../dart-core/int-class)
index) → void

[finish](renderingcontext/finish)() → void

[flush](renderingcontext/flush)() → void

[framebufferRenderbuffer](renderingcontext/framebufferrenderbuffer)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) attachment,
[int](../dart-core/int-class) renderbuffertarget,
[Renderbuffer](renderbuffer-class)? renderbuffer) → void

[framebufferTexture2D](renderingcontext/framebuffertexture2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) attachment,
[int](../dart-core/int-class) textarget, [Texture](texture-class)?
texture, [int](../dart-core/int-class) level) → void

[frontFace](renderingcontext/frontface)([int](../dart-core/int-class)
mode) → void

[generateMipmap](renderingcontext/generatemipmap)([int](../dart-core/int-class)
target) → void

[getActiveAttrib](renderingcontext/getactiveattrib)([Program](program-class)
program, [int](../dart-core/int-class) index) →
[ActiveInfo](activeinfo-class)

[getActiveUniform](renderingcontext/getactiveuniform)([Program](program-class)
program, [int](../dart-core/int-class) index) →
[ActiveInfo](activeinfo-class)

[getAttachedShaders](renderingcontext/getattachedshaders)([Program](program-class)
program) → [List](../dart-core/list-class)\<[Shader](shader-class)\>?

[getAttribLocation](renderingcontext/getattriblocation)([Program](program-class)
program, [String](../dart-core/string-class) name) →
[int](../dart-core/int-class)

[getBufferParameter](renderingcontext/getbufferparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'int\|Null\'), \@Returns(\'int\|Null\')
:::

[getContextAttributes](renderingcontext/getcontextattributes)() →
[Map](../dart-core/map-class)?

::: {.features}
\@Creates(\'ContextAttributes\|Null\')
:::

[getError](renderingcontext/geterror)() → [int](../dart-core/int-class)

[getExtension](renderingcontext/getextension)([String](../dart-core/string-class)
name) → [Object](../dart-core/object-class)?

[getFramebufferAttachmentParameter](renderingcontext/getframebufferattachmentparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) attachment,
[int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'int\|Renderbuffer\|Texture\|Null\'),
\@Returns(\'int\|Renderbuffer\|Texture\|Null\')
:::

[getParameter](renderingcontext/getparameter)([int](../dart-core/int-class)
pname) → [Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\|Framebuffer\|Renderbuffer\|Texture\'),
\@Returns(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\|Framebuffer\|Renderbuffer\|Texture\')
:::

[getProgramInfoLog](renderingcontext/getprograminfolog)([Program](program-class)
program) → [String](../dart-core/string-class)?

[getProgramParameter](renderingcontext/getprogramparameter)([Program](program-class)
program, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'int\|bool\|Null\'), \@Returns(\'int\|bool\|Null\')
:::

[getRenderbufferParameter](renderingcontext/getrenderbufferparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'int\|Null\'), \@Returns(\'int\|Null\')
:::

[getShaderInfoLog](renderingcontext/getshaderinfolog)([Shader](shader-class)
shader) → [String](../dart-core/string-class)?

[getShaderParameter](renderingcontext/getshaderparameter)([Shader](shader-class)
shader, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'int\|bool\|Null\'), \@Returns(\'int\|bool\|Null\')
:::

[getShaderPrecisionFormat](renderingcontext/getshaderprecisionformat)([int](../dart-core/int-class)
shadertype, [int](../dart-core/int-class) precisiontype) →
[ShaderPrecisionFormat](shaderprecisionformat-class)

[getShaderSource](renderingcontext/getshadersource)([Shader](shader-class)
shader) → [String](../dart-core/string-class)?

[getSupportedExtensions](renderingcontext/getsupportedextensions)() →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?

[getTexParameter](renderingcontext/gettexparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'int\|Null\'), \@Returns(\'int\|Null\')
:::

[getUniform](renderingcontext/getuniform)([Program](program-class)
program, [UniformLocation](uniformlocation-class) location) →
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\'),
\@Returns(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\')
:::

[getUniformLocation](renderingcontext/getuniformlocation)([Program](program-class)
program, [String](../dart-core/string-class) name) →
[UniformLocation](uniformlocation-class)

[getVertexAttrib](renderingcontext/getvertexattrib)([int](../dart-core/int-class)
index, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'Null\|num\|bool\|NativeFloat32List\|Buffer\'),
\@Returns(\'Null\|num\|bool\|NativeFloat32List\|Buffer\')
:::

[getVertexAttribOffset](renderingcontext/getvertexattriboffset)([int](../dart-core/int-class)
index, [int](../dart-core/int-class) pname) →
[int](../dart-core/int-class)

[hint](renderingcontext/hint)([int](../dart-core/int-class) target,
[int](../dart-core/int-class) mode) → void

[isBuffer](renderingcontext/isbuffer)([Buffer](buffer-class)? buffer) →
[bool](../dart-core/bool-class)

[isContextLost](renderingcontext/iscontextlost)() →
[bool](../dart-core/bool-class)

[isEnabled](renderingcontext/isenabled)([int](../dart-core/int-class)
cap) → [bool](../dart-core/bool-class)

[isFramebuffer](renderingcontext/isframebuffer)([Framebuffer](framebuffer-class)?
framebuffer) → [bool](../dart-core/bool-class)

[isProgram](renderingcontext/isprogram)([Program](program-class)?
program) → [bool](../dart-core/bool-class)

[isRenderbuffer](renderingcontext/isrenderbuffer)([Renderbuffer](renderbuffer-class)?
renderbuffer) → [bool](../dart-core/bool-class)

[isShader](renderingcontext/isshader)([Shader](shader-class)? shader) →
[bool](../dart-core/bool-class)

[isTexture](renderingcontext/istexture)([Texture](texture-class)?
texture) → [bool](../dart-core/bool-class)

[lineWidth](renderingcontext/linewidth)([num](../dart-core/num-class)
width) → void

[linkProgram](renderingcontext/linkprogram)([Program](program-class)
program) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pixelStorei](renderingcontext/pixelstorei)([int](../dart-core/int-class)
pname, [int](../dart-core/int-class) param) → void

[polygonOffset](renderingcontext/polygonoffset)([num](../dart-core/num-class)
factor, [num](../dart-core/num-class) units) → void

[readPixels](renderingcontext/readpixels)([int](../dart-core/int-class)
x, [int](../dart-core/int-class) y, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
format, [int](../dart-core/int-class) type,
[TypedData](../dart-typed_data/typeddata-class)? pixels) → void

[renderbufferStorage](renderingcontext/renderbufferstorage)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height) → void

[sampleCoverage](renderingcontext/samplecoverage)([num](../dart-core/num-class)
value, [bool](../dart-core/bool-class) invert) → void

[scissor](renderingcontext/scissor)([int](../dart-core/int-class) x,
[int](../dart-core/int-class) y, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height) → void

[shaderSource](renderingcontext/shadersource)([Shader](shader-class)
shader, [String](../dart-core/string-class) string) → void

[stencilFunc](renderingcontext/stencilfunc)([int](../dart-core/int-class)
func, [int](../dart-core/int-class) ref, [int](../dart-core/int-class)
mask) → void

[stencilFuncSeparate](renderingcontext/stencilfuncseparate)([int](../dart-core/int-class)
face, [int](../dart-core/int-class) func, [int](../dart-core/int-class)
ref, [int](../dart-core/int-class) mask) → void

[stencilMask](renderingcontext/stencilmask)([int](../dart-core/int-class)
mask) → void

[stencilMaskSeparate](renderingcontext/stencilmaskseparate)([int](../dart-core/int-class)
face, [int](../dart-core/int-class) mask) → void

[stencilOp](renderingcontext/stencilop)([int](../dart-core/int-class)
fail, [int](../dart-core/int-class) zfail, [int](../dart-core/int-class)
zpass) → void

[stencilOpSeparate](renderingcontext/stencilopseparate)([int](../dart-core/int-class)
face, [int](../dart-core/int-class) fail, [int](../dart-core/int-class)
zfail, [int](../dart-core/int-class) zpass) → void

[texImage2D](renderingcontext/teximage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) format\_OR\_width,
[int](../dart-core/int-class) height\_OR\_type, dynamic
bitmap\_OR\_border\_OR\_canvas\_OR\_image\_OR\_pixels\_OR\_video,
\[[int](../dart-core/int-class)? format, [int](../dart-core/int-class)?
type, [TypedData](../dart-typed_data/typeddata-class)? pixels\]) → void

[texImage2DTyped](renderingcontext/teximage2dtyped){.deprecated}([int](../dart-core/int-class)
targetTexture, [int](../dart-core/int-class) levelOfDetail,
[int](../dart-core/int-class) internalFormat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) border,
[int](../dart-core/int-class) format, [int](../dart-core/int-class)
type, [TypedData](../dart-typed_data/typeddata-class) data) → void

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"Use texImage2D\")
:::

Sets the currently bound texture to `data`.

[texImage2DUntyped](renderingcontext/teximage2duntyped){.deprecated}([int](../dart-core/int-class)
targetTexture, [int](../dart-core/int-class) levelOfDetail,
[int](../dart-core/int-class) internalFormat,
[int](../dart-core/int-class) format, [int](../dart-core/int-class)
type, dynamic data) → void

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"Use texImage2D\")
:::

Sets the currently bound texture to `data`.

[texParameterf](renderingcontext/texparameterf)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname,
[num](../dart-core/num-class) param) → void

[texParameteri](renderingcontext/texparameteri)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname,
[int](../dart-core/int-class) param) → void

[texSubImage2D](renderingcontext/texsubimage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) format\_OR\_width,
[int](../dart-core/int-class) height\_OR\_type, dynamic
bitmap\_OR\_canvas\_OR\_format\_OR\_image\_OR\_pixels\_OR\_video,
\[[int](../dart-core/int-class)? type,
[TypedData](../dart-typed_data/typeddata-class)? pixels\]) → void

[texSubImage2DTyped](renderingcontext/texsubimage2dtyped){.deprecated}([int](../dart-core/int-class)
targetTexture, [int](../dart-core/int-class) levelOfDetail,
[int](../dart-core/int-class) xOffset, [int](../dart-core/int-class)
yOffset, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
border, [int](../dart-core/int-class) format,
[int](../dart-core/int-class) type,
[TypedData](../dart-typed_data/typeddata-class) data) → void

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"Use texSubImage2D\")
:::

Updates a sub-rectangle of the currently bound texture to `data`.

[texSubImage2DUntyped](renderingcontext/texsubimage2duntyped){.deprecated}([int](../dart-core/int-class)
targetTexture, [int](../dart-core/int-class) levelOfDetail,
[int](../dart-core/int-class) xOffset, [int](../dart-core/int-class)
yOffset, [int](../dart-core/int-class) format,
[int](../dart-core/int-class) type, dynamic data) → void

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"Use texSubImage2D\")
:::

Updates a sub-rectangle of the currently bound texture to `data`.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[uniform1f](renderingcontext/uniform1f)([UniformLocation](uniformlocation-class)?
location, [num](../dart-core/num-class) x) → void

[uniform1fv](renderingcontext/uniform1fv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform1i](renderingcontext/uniform1i)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) x) → void

[uniform1iv](renderingcontext/uniform1iv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform2f](renderingcontext/uniform2f)([UniformLocation](uniformlocation-class)?
location, [num](../dart-core/num-class) x, [num](../dart-core/num-class)
y) → void

[uniform2fv](renderingcontext/uniform2fv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform2i](renderingcontext/uniform2i)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) x, [int](../dart-core/int-class)
y) → void

[uniform2iv](renderingcontext/uniform2iv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform3f](renderingcontext/uniform3f)([UniformLocation](uniformlocation-class)?
location, [num](../dart-core/num-class) x, [num](../dart-core/num-class)
y, [num](../dart-core/num-class) z) → void

[uniform3fv](renderingcontext/uniform3fv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform3i](renderingcontext/uniform3i)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) x, [int](../dart-core/int-class)
y, [int](../dart-core/int-class) z) → void

[uniform3iv](renderingcontext/uniform3iv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform4f](renderingcontext/uniform4f)([UniformLocation](uniformlocation-class)?
location, [num](../dart-core/num-class) x, [num](../dart-core/num-class)
y, [num](../dart-core/num-class) z, [num](../dart-core/num-class) w) →
void

[uniform4fv](renderingcontext/uniform4fv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform4i](renderingcontext/uniform4i)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) x, [int](../dart-core/int-class)
y, [int](../dart-core/int-class) z, [int](../dart-core/int-class) w) →
void

[uniform4iv](renderingcontext/uniform4iv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniformMatrix2fv](renderingcontext/uniformmatrix2fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array) →
void

[uniformMatrix3fv](renderingcontext/uniformmatrix3fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array) →
void

[uniformMatrix4fv](renderingcontext/uniformmatrix4fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array) →
void

[useProgram](renderingcontext/useprogram)([Program](program-class)?
program) → void

[validateProgram](renderingcontext/validateprogram)([Program](program-class)
program) → void

[vertexAttrib1f](renderingcontext/vertexattrib1f)([int](../dart-core/int-class)
indx, [num](../dart-core/num-class) x) → void

[vertexAttrib1fv](renderingcontext/vertexattrib1fv)([int](../dart-core/int-class)
indx, dynamic values) → void

[vertexAttrib2f](renderingcontext/vertexattrib2f)([int](../dart-core/int-class)
indx, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y)
→ void

[vertexAttrib2fv](renderingcontext/vertexattrib2fv)([int](../dart-core/int-class)
indx, dynamic values) → void

[vertexAttrib3f](renderingcontext/vertexattrib3f)([int](../dart-core/int-class)
indx, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y,
[num](../dart-core/num-class) z) → void

[vertexAttrib3fv](renderingcontext/vertexattrib3fv)([int](../dart-core/int-class)
indx, dynamic values) → void

[vertexAttrib4f](renderingcontext/vertexattrib4f)([int](../dart-core/int-class)
indx, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y,
[num](../dart-core/num-class) z, [num](../dart-core/num-class) w) → void

[vertexAttrib4fv](renderingcontext/vertexattrib4fv)([int](../dart-core/int-class)
indx, dynamic values) → void

[vertexAttribPointer](renderingcontext/vertexattribpointer)([int](../dart-core/int-class)
indx, [int](../dart-core/int-class) size, [int](../dart-core/int-class)
type, [bool](../dart-core/bool-class) normalized,
[int](../dart-core/int-class) stride, [int](../dart-core/int-class)
offset) → void

[viewport](renderingcontext/viewport)([int](../dart-core/int-class) x,
[int](../dart-core/int-class) y, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height) → void

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Properties
-----------------

[supported](renderingcontext/supported) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext-class.html>
:::
