[dart:web\_gl](../dart-web_gl/dart-web_gl-library){._links-link}

RenderingContext2 class
=======================

Annotations

:   -   \@Native(\"WebGL2RenderingContext\")

Properties {#instance-properties}
----------

[canvas](renderingcontext2/canvas) → [Canvas](canvas-class)?

::: {.features}
read-only
:::

[drawingBufferHeight](renderingcontext2/drawingbufferheight) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[drawingBufferWidth](renderingcontext2/drawingbufferwidth) →
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

[activeTexture](renderingcontext2/activetexture)([int](../dart-core/int-class)
texture) → void

[attachShader](renderingcontext2/attachshader)([Program](program-class)
program, [Shader](shader-class) shader) → void

[beginQuery](renderingcontext2/beginquery)([int](../dart-core/int-class)
target, [Query](query-class) query) → void

[beginTransformFeedback](renderingcontext2/begintransformfeedback)([int](../dart-core/int-class)
primitiveMode) → void

[bindAttribLocation](renderingcontext2/bindattriblocation)([Program](program-class)
program, [int](../dart-core/int-class) index,
[String](../dart-core/string-class) name) → void

[bindBuffer](renderingcontext2/bindbuffer)([int](../dart-core/int-class)
target, [Buffer](buffer-class)? buffer) → void

[bindBufferBase](renderingcontext2/bindbufferbase)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) index, [Buffer](buffer-class)?
buffer) → void

[bindBufferRange](renderingcontext2/bindbufferrange)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) index, [Buffer](buffer-class)?
buffer, [int](../dart-core/int-class) offset,
[int](../dart-core/int-class) size) → void

[bindFramebuffer](renderingcontext2/bindframebuffer)([int](../dart-core/int-class)
target, [Framebuffer](framebuffer-class)? framebuffer) → void

[bindRenderbuffer](renderingcontext2/bindrenderbuffer)([int](../dart-core/int-class)
target, [Renderbuffer](renderbuffer-class)? renderbuffer) → void

[bindSampler](renderingcontext2/bindsampler)([int](../dart-core/int-class)
unit, [Sampler](sampler-class)? sampler) → void

[bindTexture](renderingcontext2/bindtexture)([int](../dart-core/int-class)
target, [Texture](texture-class)? texture) → void

[bindTransformFeedback](renderingcontext2/bindtransformfeedback)([int](../dart-core/int-class)
target, [TransformFeedback](transformfeedback-class)? feedback) → void

[bindVertexArray](renderingcontext2/bindvertexarray)([VertexArrayObject](vertexarrayobject-class)?
vertexArray) → void

[blendColor](renderingcontext2/blendcolor)([num](../dart-core/num-class)
red, [num](../dart-core/num-class) green, [num](../dart-core/num-class)
blue, [num](../dart-core/num-class) alpha) → void

[blendEquation](renderingcontext2/blendequation)([int](../dart-core/int-class)
mode) → void

[blendEquationSeparate](renderingcontext2/blendequationseparate)([int](../dart-core/int-class)
modeRGB, [int](../dart-core/int-class) modeAlpha) → void

[blendFunc](renderingcontext2/blendfunc)([int](../dart-core/int-class)
sfactor, [int](../dart-core/int-class) dfactor) → void

[blendFuncSeparate](renderingcontext2/blendfuncseparate)([int](../dart-core/int-class)
srcRGB, [int](../dart-core/int-class) dstRGB,
[int](../dart-core/int-class) srcAlpha, [int](../dart-core/int-class)
dstAlpha) → void

[blitFramebuffer](renderingcontext2/blitframebuffer)([int](../dart-core/int-class)
srcX0, [int](../dart-core/int-class) srcY0,
[int](../dart-core/int-class) srcX1, [int](../dart-core/int-class)
srcY1, [int](../dart-core/int-class) dstX0,
[int](../dart-core/int-class) dstY0, [int](../dart-core/int-class)
dstX1, [int](../dart-core/int-class) dstY1,
[int](../dart-core/int-class) mask, [int](../dart-core/int-class)
filter) → void

[bufferData](renderingcontext2/bufferdata)([int](../dart-core/int-class)
target, dynamic data\_OR\_size, [int](../dart-core/int-class) usage) →
void

[bufferData2](renderingcontext2/bufferdata2)([int](../dart-core/int-class)
target, [TypedData](../dart-typed_data/typeddata-class) srcData,
[int](../dart-core/int-class) usage, [int](../dart-core/int-class)
srcOffset, \[[int](../dart-core/int-class)? length\]) → void

::: {.features}
\@JSName(\'bufferData\')
:::

[bufferSubData](renderingcontext2/buffersubdata)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) offset, dynamic data) → void

[bufferSubData2](renderingcontext2/buffersubdata2)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) dstByteOffset,
[TypedData](../dart-typed_data/typeddata-class) srcData,
[int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? length\]) → void

::: {.features}
\@JSName(\'bufferSubData\')
:::

[checkFramebufferStatus](renderingcontext2/checkframebufferstatus)([int](../dart-core/int-class)
target) → [int](../dart-core/int-class)

[clear](renderingcontext2/clear)([int](../dart-core/int-class) mask) →
void

[clearBufferfi](renderingcontext2/clearbufferfi)([int](../dart-core/int-class)
buffer, [int](../dart-core/int-class) drawbuffer,
[num](../dart-core/num-class) depth, [int](../dart-core/int-class)
stencil) → void

[clearBufferfv](renderingcontext2/clearbufferfv)([int](../dart-core/int-class)
buffer, [int](../dart-core/int-class) drawbuffer, dynamic value,
\[[int](../dart-core/int-class)? srcOffset\]) → void

[clearBufferiv](renderingcontext2/clearbufferiv)([int](../dart-core/int-class)
buffer, [int](../dart-core/int-class) drawbuffer, dynamic value,
\[[int](../dart-core/int-class)? srcOffset\]) → void

[clearBufferuiv](renderingcontext2/clearbufferuiv)([int](../dart-core/int-class)
buffer, [int](../dart-core/int-class) drawbuffer, dynamic value,
\[[int](../dart-core/int-class)? srcOffset\]) → void

[clearColor](renderingcontext2/clearcolor)([num](../dart-core/num-class)
red, [num](../dart-core/num-class) green, [num](../dart-core/num-class)
blue, [num](../dart-core/num-class) alpha) → void

[clearDepth](renderingcontext2/cleardepth)([num](../dart-core/num-class)
depth) → void

[clearStencil](renderingcontext2/clearstencil)([int](../dart-core/int-class)
s) → void

[clientWaitSync](renderingcontext2/clientwaitsync)([Sync](sync-class)
sync, [int](../dart-core/int-class) flags, [int](../dart-core/int-class)
timeout) → [int](../dart-core/int-class)

[colorMask](renderingcontext2/colormask)([bool](../dart-core/bool-class)
red, [bool](../dart-core/bool-class) green,
[bool](../dart-core/bool-class) blue, [bool](../dart-core/bool-class)
alpha) → void

[commit](renderingcontext2/commit)() →
[Future](../dart-async/future-class)

[compileShader](renderingcontext2/compileshader)([Shader](shader-class)
shader) → void

[compressedTexImage2D](renderingcontext2/compressedteximage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) border,
[TypedData](../dart-typed_data/typeddata-class) data) → void

[compressedTexImage2D2](renderingcontext2/compressedteximage2d2)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) border,
[TypedData](../dart-typed_data/typeddata-class) data,
[int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLengthOverride\]) → void

::: {.features}
\@JSName(\'compressedTexImage2D\')
:::

[compressedTexImage2D3](renderingcontext2/compressedteximage2d3)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) border,
[int](../dart-core/int-class) imageSize, [int](../dart-core/int-class)
offset) → void

::: {.features}
\@JSName(\'compressedTexImage2D\')
:::

[compressedTexImage3D](renderingcontext2/compressedteximage3d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) depth,
[int](../dart-core/int-class) border,
[TypedData](../dart-typed_data/typeddata-class) data,
\[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLengthOverride\]) → void

[compressedTexImage3D2](renderingcontext2/compressedteximage3d2)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) depth,
[int](../dart-core/int-class) border, [int](../dart-core/int-class)
imageSize, [int](../dart-core/int-class) offset) → void

::: {.features}
\@JSName(\'compressedTexImage3D\')
:::

[compressedTexSubImage2D](renderingcontext2/compressedtexsubimage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
format, [TypedData](../dart-typed_data/typeddata-class) data) → void

[compressedTexSubImage2D2](renderingcontext2/compressedtexsubimage2d2)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
format, [TypedData](../dart-typed_data/typeddata-class) data,
[int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLengthOverride\]) → void

::: {.features}
\@JSName(\'compressedTexSubImage2D\')
:::

[compressedTexSubImage2D3](renderingcontext2/compressedtexsubimage2d3)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
format, [int](../dart-core/int-class) imageSize,
[int](../dart-core/int-class) offset) → void

::: {.features}
\@JSName(\'compressedTexSubImage2D\')
:::

[compressedTexSubImage3D](renderingcontext2/compressedtexsubimage3d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) zoffset,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) depth,
[int](../dart-core/int-class) format,
[TypedData](../dart-typed_data/typeddata-class) data,
\[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLengthOverride\]) → void

[compressedTexSubImage3D2](renderingcontext2/compressedtexsubimage3d2)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) zoffset,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) depth,
[int](../dart-core/int-class) format, [int](../dart-core/int-class)
imageSize, [int](../dart-core/int-class) offset) → void

::: {.features}
\@JSName(\'compressedTexSubImage3D\')
:::

[copyBufferSubData](renderingcontext2/copybuffersubdata)([int](../dart-core/int-class)
readTarget, [int](../dart-core/int-class) writeTarget,
[int](../dart-core/int-class) readOffset, [int](../dart-core/int-class)
writeOffset, [int](../dart-core/int-class) size) → void

[copyTexImage2D](renderingcontext2/copyteximage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) x, [int](../dart-core/int-class) y,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) border) → void

[copyTexSubImage2D](renderingcontext2/copytexsubimage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) x, [int](../dart-core/int-class)
y, [int](../dart-core/int-class) width, [int](../dart-core/int-class)
height) → void

[copyTexSubImage3D](renderingcontext2/copytexsubimage3d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) zoffset,
[int](../dart-core/int-class) x, [int](../dart-core/int-class) y,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height) → void

[createBuffer](renderingcontext2/createbuffer)() →
[Buffer](buffer-class)

[createFramebuffer](renderingcontext2/createframebuffer)() →
[Framebuffer](framebuffer-class)

[createProgram](renderingcontext2/createprogram)() →
[Program](program-class)

[createQuery](renderingcontext2/createquery)() → [Query](query-class)?

[createRenderbuffer](renderingcontext2/createrenderbuffer)() →
[Renderbuffer](renderbuffer-class)

[createSampler](renderingcontext2/createsampler)() →
[Sampler](sampler-class)?

[createShader](renderingcontext2/createshader)([int](../dart-core/int-class)
type) → [Shader](shader-class)

[createTexture](renderingcontext2/createtexture)() →
[Texture](texture-class)

[createTransformFeedback](renderingcontext2/createtransformfeedback)() →
[TransformFeedback](transformfeedback-class)?

[createVertexArray](renderingcontext2/createvertexarray)() →
[VertexArrayObject](vertexarrayobject-class)?

[cullFace](renderingcontext2/cullface)([int](../dart-core/int-class)
mode) → void

[deleteBuffer](renderingcontext2/deletebuffer)([Buffer](buffer-class)?
buffer) → void

[deleteFramebuffer](renderingcontext2/deleteframebuffer)([Framebuffer](framebuffer-class)?
framebuffer) → void

[deleteProgram](renderingcontext2/deleteprogram)([Program](program-class)?
program) → void

[deleteQuery](renderingcontext2/deletequery)([Query](query-class)?
query) → void

[deleteRenderbuffer](renderingcontext2/deleterenderbuffer)([Renderbuffer](renderbuffer-class)?
renderbuffer) → void

[deleteSampler](renderingcontext2/deletesampler)([Sampler](sampler-class)?
sampler) → void

[deleteShader](renderingcontext2/deleteshader)([Shader](shader-class)?
shader) → void

[deleteSync](renderingcontext2/deletesync)([Sync](sync-class)? sync) →
void

[deleteTexture](renderingcontext2/deletetexture)([Texture](texture-class)?
texture) → void

[deleteTransformFeedback](renderingcontext2/deletetransformfeedback)([TransformFeedback](transformfeedback-class)?
feedback) → void

[deleteVertexArray](renderingcontext2/deletevertexarray)([VertexArrayObject](vertexarrayobject-class)?
vertexArray) → void

[depthFunc](renderingcontext2/depthfunc)([int](../dart-core/int-class)
func) → void

[depthMask](renderingcontext2/depthmask)([bool](../dart-core/bool-class)
flag) → void

[depthRange](renderingcontext2/depthrange)([num](../dart-core/num-class)
zNear, [num](../dart-core/num-class) zFar) → void

[detachShader](renderingcontext2/detachshader)([Program](program-class)
program, [Shader](shader-class) shader) → void

[disable](renderingcontext2/disable)([int](../dart-core/int-class) cap)
→ void

[disableVertexAttribArray](renderingcontext2/disablevertexattribarray)([int](../dart-core/int-class)
index) → void

[drawArrays](renderingcontext2/drawarrays)([int](../dart-core/int-class)
mode, [int](../dart-core/int-class) first, [int](../dart-core/int-class)
count) → void

[drawArraysInstanced](renderingcontext2/drawarraysinstanced)([int](../dart-core/int-class)
mode, [int](../dart-core/int-class) first, [int](../dart-core/int-class)
count, [int](../dart-core/int-class) instanceCount) → void

[drawBuffers](renderingcontext2/drawbuffers)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffers) → void

[drawElements](renderingcontext2/drawelements)([int](../dart-core/int-class)
mode, [int](../dart-core/int-class) count, [int](../dart-core/int-class)
type, [int](../dart-core/int-class) offset) → void

[drawElementsInstanced](renderingcontext2/drawelementsinstanced)([int](../dart-core/int-class)
mode, [int](../dart-core/int-class) count, [int](../dart-core/int-class)
type, [int](../dart-core/int-class) offset,
[int](../dart-core/int-class) instanceCount) → void

[drawRangeElements](renderingcontext2/drawrangeelements)([int](../dart-core/int-class)
mode, [int](../dart-core/int-class) start, [int](../dart-core/int-class)
end, [int](../dart-core/int-class) count, [int](../dart-core/int-class)
type, [int](../dart-core/int-class) offset) → void

[enable](renderingcontext2/enable)([int](../dart-core/int-class) cap) →
void

[enableVertexAttribArray](renderingcontext2/enablevertexattribarray)([int](../dart-core/int-class)
index) → void

[endQuery](renderingcontext2/endquery)([int](../dart-core/int-class)
target) → void

[endTransformFeedback](renderingcontext2/endtransformfeedback)() → void

[fenceSync](renderingcontext2/fencesync)([int](../dart-core/int-class)
condition, [int](../dart-core/int-class) flags) → [Sync](sync-class)?

[finish](renderingcontext2/finish)() → void

[flush](renderingcontext2/flush)() → void

[framebufferRenderbuffer](renderingcontext2/framebufferrenderbuffer)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) attachment,
[int](../dart-core/int-class) renderbuffertarget,
[Renderbuffer](renderbuffer-class)? renderbuffer) → void

[framebufferTexture2D](renderingcontext2/framebuffertexture2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) attachment,
[int](../dart-core/int-class) textarget, [Texture](texture-class)?
texture, [int](../dart-core/int-class) level) → void

[framebufferTextureLayer](renderingcontext2/framebuffertexturelayer)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) attachment,
[Texture](texture-class)? texture, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) layer) → void

[frontFace](renderingcontext2/frontface)([int](../dart-core/int-class)
mode) → void

[generateMipmap](renderingcontext2/generatemipmap)([int](../dart-core/int-class)
target) → void

[getActiveAttrib](renderingcontext2/getactiveattrib)([Program](program-class)
program, [int](../dart-core/int-class) index) →
[ActiveInfo](activeinfo-class)

[getActiveUniform](renderingcontext2/getactiveuniform)([Program](program-class)
program, [int](../dart-core/int-class) index) →
[ActiveInfo](activeinfo-class)

[getActiveUniformBlockName](renderingcontext2/getactiveuniformblockname)([Program](program-class)
program, [int](../dart-core/int-class) uniformBlockIndex) →
[String](../dart-core/string-class)?

[getActiveUniformBlockParameter](renderingcontext2/getactiveuniformblockparameter)([Program](program-class)
program, [int](../dart-core/int-class) uniformBlockIndex,
[int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getActiveUniforms](renderingcontext2/getactiveuniforms)([Program](program-class)
program,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
uniformIndices, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getAttachedShaders](renderingcontext2/getattachedshaders)([Program](program-class)
program) → [List](../dart-core/list-class)\<[Shader](shader-class)\>?

[getAttribLocation](renderingcontext2/getattriblocation)([Program](program-class)
program, [String](../dart-core/string-class) name) →
[int](../dart-core/int-class)

[getBufferParameter](renderingcontext2/getbufferparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getBufferSubData](renderingcontext2/getbuffersubdata)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) srcByteOffset,
[TypedData](../dart-typed_data/typeddata-class) dstData,
\[[int](../dart-core/int-class)? dstOffset,
[int](../dart-core/int-class)? length\]) → void

[getContextAttributes](renderingcontext2/getcontextattributes)() →
[Map](../dart-core/map-class)?

[getError](renderingcontext2/geterror)() → [int](../dart-core/int-class)

[getExtension](renderingcontext2/getextension)([String](../dart-core/string-class)
name) → [Object](../dart-core/object-class)?

[getFragDataLocation](renderingcontext2/getfragdatalocation)([Program](program-class)
program, [String](../dart-core/string-class) name) →
[int](../dart-core/int-class)

[getFramebufferAttachmentParameter](renderingcontext2/getframebufferattachmentparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) attachment,
[int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getIndexedParameter](renderingcontext2/getindexedparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) index) →
[Object](../dart-core/object-class)?

[getInternalformatParameter](renderingcontext2/getinternalformatparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getParameter](renderingcontext2/getparameter)([int](../dart-core/int-class)
pname) → [Object](../dart-core/object-class)?

[getProgramInfoLog](renderingcontext2/getprograminfolog)([Program](program-class)
program) → [String](../dart-core/string-class)?

[getProgramParameter](renderingcontext2/getprogramparameter)([Program](program-class)
program, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getQuery](renderingcontext2/getquery)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getQueryParameter](renderingcontext2/getqueryparameter)([Query](query-class)
query, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getRenderbufferParameter](renderingcontext2/getrenderbufferparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getSamplerParameter](renderingcontext2/getsamplerparameter)([Sampler](sampler-class)
sampler, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getShaderInfoLog](renderingcontext2/getshaderinfolog)([Shader](shader-class)
shader) → [String](../dart-core/string-class)?

[getShaderParameter](renderingcontext2/getshaderparameter)([Shader](shader-class)
shader, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getShaderPrecisionFormat](renderingcontext2/getshaderprecisionformat)([int](../dart-core/int-class)
shadertype, [int](../dart-core/int-class) precisiontype) →
[ShaderPrecisionFormat](shaderprecisionformat-class)

[getShaderSource](renderingcontext2/getshadersource)([Shader](shader-class)
shader) → [String](../dart-core/string-class)?

[getSupportedExtensions](renderingcontext2/getsupportedextensions)() →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?

[getSyncParameter](renderingcontext2/getsyncparameter)([Sync](sync-class)
sync, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getTexParameter](renderingcontext2/gettexparameter)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getTransformFeedbackVarying](renderingcontext2/gettransformfeedbackvarying)([Program](program-class)
program, [int](../dart-core/int-class) index) →
[ActiveInfo](activeinfo-class)?

[getUniform](renderingcontext2/getuniform)([Program](program-class)
program, [UniformLocation](uniformlocation-class) location) →
[Object](../dart-core/object-class)?

[getUniformBlockIndex](renderingcontext2/getuniformblockindex)([Program](program-class)
program, [String](../dart-core/string-class) uniformBlockName) →
[int](../dart-core/int-class)

[getUniformIndices](renderingcontext2/getuniformindices)([Program](program-class)
program,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>
uniformNames) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?

[getUniformLocation](renderingcontext2/getuniformlocation)([Program](program-class)
program, [String](../dart-core/string-class) name) →
[UniformLocation](uniformlocation-class)

[getVertexAttrib](renderingcontext2/getvertexattrib)([int](../dart-core/int-class)
index, [int](../dart-core/int-class) pname) →
[Object](../dart-core/object-class)?

[getVertexAttribOffset](renderingcontext2/getvertexattriboffset)([int](../dart-core/int-class)
index, [int](../dart-core/int-class) pname) →
[int](../dart-core/int-class)

[hint](renderingcontext2/hint)([int](../dart-core/int-class) target,
[int](../dart-core/int-class) mode) → void

[invalidateFramebuffer](renderingcontext2/invalidateframebuffer)([int](../dart-core/int-class)
target, [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
attachments) → void

[invalidateSubFramebuffer](renderingcontext2/invalidatesubframebuffer)([int](../dart-core/int-class)
target, [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
attachments, [int](../dart-core/int-class) x,
[int](../dart-core/int-class) y, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height) → void

[isBuffer](renderingcontext2/isbuffer)([Buffer](buffer-class)? buffer) →
[bool](../dart-core/bool-class)

[isContextLost](renderingcontext2/iscontextlost)() →
[bool](../dart-core/bool-class)

[isEnabled](renderingcontext2/isenabled)([int](../dart-core/int-class)
cap) → [bool](../dart-core/bool-class)

[isFramebuffer](renderingcontext2/isframebuffer)([Framebuffer](framebuffer-class)?
framebuffer) → [bool](../dart-core/bool-class)

[isProgram](renderingcontext2/isprogram)([Program](program-class)?
program) → [bool](../dart-core/bool-class)

[isQuery](renderingcontext2/isquery)([Query](query-class)? query) →
[bool](../dart-core/bool-class)

[isRenderbuffer](renderingcontext2/isrenderbuffer)([Renderbuffer](renderbuffer-class)?
renderbuffer) → [bool](../dart-core/bool-class)

[isSampler](renderingcontext2/issampler)([Sampler](sampler-class)?
sampler) → [bool](../dart-core/bool-class)

[isShader](renderingcontext2/isshader)([Shader](shader-class)? shader) →
[bool](../dart-core/bool-class)

[isSync](renderingcontext2/issync)([Sync](sync-class)? sync) →
[bool](../dart-core/bool-class)

[isTexture](renderingcontext2/istexture)([Texture](texture-class)?
texture) → [bool](../dart-core/bool-class)

[isTransformFeedback](renderingcontext2/istransformfeedback)([TransformFeedback](transformfeedback-class)?
feedback) → [bool](../dart-core/bool-class)

[isVertexArray](renderingcontext2/isvertexarray)([VertexArrayObject](vertexarrayobject-class)?
vertexArray) → [bool](../dart-core/bool-class)

[lineWidth](renderingcontext2/linewidth)([num](../dart-core/num-class)
width) → void

[linkProgram](renderingcontext2/linkprogram)([Program](program-class)
program) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pauseTransformFeedback](renderingcontext2/pausetransformfeedback)() →
void

[pixelStorei](renderingcontext2/pixelstorei)([int](../dart-core/int-class)
pname, [int](../dart-core/int-class) param) → void

[polygonOffset](renderingcontext2/polygonoffset)([num](../dart-core/num-class)
factor, [num](../dart-core/num-class) units) → void

[readBuffer](renderingcontext2/readbuffer)([int](../dart-core/int-class)
mode) → void

[readPixels](renderingcontext2/readpixels)([int](../dart-core/int-class)
x, [int](../dart-core/int-class) y, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
format, [int](../dart-core/int-class) type,
[TypedData](../dart-typed_data/typeddata-class) pixels) → void

[readPixels2](renderingcontext2/readpixels2)([int](../dart-core/int-class)
x, [int](../dart-core/int-class) y, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
format, [int](../dart-core/int-class) type, dynamic dstData\_OR\_offset,
\[[int](../dart-core/int-class)? offset\]) → void

::: {.features}
\@JSName(\'readPixels\')
:::

[renderbufferStorage](renderingcontext2/renderbufferstorage)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height) → void

[renderbufferStorageMultisample](renderingcontext2/renderbufferstoragemultisample)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) samples,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height) → void

[resumeTransformFeedback](renderingcontext2/resumetransformfeedback)() →
void

[sampleCoverage](renderingcontext2/samplecoverage)([num](../dart-core/num-class)
value, [bool](../dart-core/bool-class) invert) → void

[samplerParameterf](renderingcontext2/samplerparameterf)([Sampler](sampler-class)
sampler, [int](../dart-core/int-class) pname,
[num](../dart-core/num-class) param) → void

[samplerParameteri](renderingcontext2/samplerparameteri)([Sampler](sampler-class)
sampler, [int](../dart-core/int-class) pname,
[int](../dart-core/int-class) param) → void

[scissor](renderingcontext2/scissor)([int](../dart-core/int-class) x,
[int](../dart-core/int-class) y, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height) → void

[shaderSource](renderingcontext2/shadersource)([Shader](shader-class)
shader, [String](../dart-core/string-class) string) → void

[stencilFunc](renderingcontext2/stencilfunc)([int](../dart-core/int-class)
func, [int](../dart-core/int-class) ref, [int](../dart-core/int-class)
mask) → void

[stencilFuncSeparate](renderingcontext2/stencilfuncseparate)([int](../dart-core/int-class)
face, [int](../dart-core/int-class) func, [int](../dart-core/int-class)
ref, [int](../dart-core/int-class) mask) → void

[stencilMask](renderingcontext2/stencilmask)([int](../dart-core/int-class)
mask) → void

[stencilMaskSeparate](renderingcontext2/stencilmaskseparate)([int](../dart-core/int-class)
face, [int](../dart-core/int-class) mask) → void

[stencilOp](renderingcontext2/stencilop)([int](../dart-core/int-class)
fail, [int](../dart-core/int-class) zfail, [int](../dart-core/int-class)
zpass) → void

[stencilOpSeparate](renderingcontext2/stencilopseparate)([int](../dart-core/int-class)
face, [int](../dart-core/int-class) fail, [int](../dart-core/int-class)
zfail, [int](../dart-core/int-class) zpass) → void

[texImage2D](renderingcontext2/teximage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) format\_OR\_width,
[int](../dart-core/int-class) height\_OR\_type, dynamic
bitmap\_OR\_border\_OR\_canvas\_OR\_image\_OR\_pixels\_OR\_video,
\[[int](../dart-core/int-class)? format, [int](../dart-core/int-class)?
type, [TypedData](../dart-typed_data/typeddata-class)? pixels\]) → void

[texImage2D2](renderingcontext2/teximage2d2)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) border,
[int](../dart-core/int-class) format, [int](../dart-core/int-class)
type, dynamic
bitmap\_OR\_canvas\_OR\_data\_OR\_image\_OR\_offset\_OR\_srcData\_OR\_video,
\[[int](../dart-core/int-class)? srcOffset\]) → void

[texImage3D](renderingcontext2/teximage3d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) depth,
[int](../dart-core/int-class) border, [int](../dart-core/int-class)
format, [int](../dart-core/int-class) type, dynamic
bitmap\_OR\_canvas\_OR\_data\_OR\_image\_OR\_offset\_OR\_pixels\_OR\_video,
\[[int](../dart-core/int-class)? srcOffset\]) → void

[texParameterf](renderingcontext2/texparameterf)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname,
[num](../dart-core/num-class) param) → void

[texParameteri](renderingcontext2/texparameteri)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) pname,
[int](../dart-core/int-class) param) → void

[texStorage2D](renderingcontext2/texstorage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) levels,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height) → void

[texStorage3D](renderingcontext2/texstorage3d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) levels,
[int](../dart-core/int-class) internalformat,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) depth) → void

[texSubImage2D](renderingcontext2/texsubimage2d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) format\_OR\_width,
[int](../dart-core/int-class) height\_OR\_type, dynamic
bitmap\_OR\_canvas\_OR\_format\_OR\_image\_OR\_pixels\_OR\_video,
\[[int](../dart-core/int-class)? type,
[TypedData](../dart-typed_data/typeddata-class)? pixels\]) → void

[texSubImage2D2](renderingcontext2/texsubimage2d2)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height, [int](../dart-core/int-class)
format, [int](../dart-core/int-class) type, dynamic
bitmap\_OR\_canvas\_OR\_data\_OR\_image\_OR\_offset\_OR\_srcData\_OR\_video,
\[[int](../dart-core/int-class)? srcOffset\]) → void

[texSubImage3D](renderingcontext2/texsubimage3d)([int](../dart-core/int-class)
target, [int](../dart-core/int-class) level,
[int](../dart-core/int-class) xoffset, [int](../dart-core/int-class)
yoffset, [int](../dart-core/int-class) zoffset,
[int](../dart-core/int-class) width, [int](../dart-core/int-class)
height, [int](../dart-core/int-class) depth,
[int](../dart-core/int-class) format, [int](../dart-core/int-class)
type, dynamic
bitmap\_OR\_canvas\_OR\_data\_OR\_image\_OR\_offset\_OR\_pixels\_OR\_video,
\[[int](../dart-core/int-class)? srcOffset\]) → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transformFeedbackVaryings](renderingcontext2/transformfeedbackvaryings)([Program](program-class)
program,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>
varyings, [int](../dart-core/int-class) bufferMode) → void

[uniform1f](renderingcontext2/uniform1f)([UniformLocation](uniformlocation-class)?
location, [num](../dart-core/num-class) x) → void

[uniform1fv](renderingcontext2/uniform1fv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform1fv2](renderingcontext2/uniform1fv2)([UniformLocation](uniformlocation-class)?
location, dynamic v, [int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniform1fv\')
:::

[uniform1i](renderingcontext2/uniform1i)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) x) → void

[uniform1iv](renderingcontext2/uniform1iv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform1iv2](renderingcontext2/uniform1iv2)([UniformLocation](uniformlocation-class)?
location, dynamic v, [int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniform1iv\')
:::

[uniform1ui](renderingcontext2/uniform1ui)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) v0) → void

[uniform1uiv](renderingcontext2/uniform1uiv)([UniformLocation](uniformlocation-class)?
location, dynamic v, \[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniform2f](renderingcontext2/uniform2f)([UniformLocation](uniformlocation-class)?
location, [num](../dart-core/num-class) x, [num](../dart-core/num-class)
y) → void

[uniform2fv](renderingcontext2/uniform2fv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform2fv2](renderingcontext2/uniform2fv2)([UniformLocation](uniformlocation-class)?
location, dynamic v, [int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniform2fv\')
:::

[uniform2i](renderingcontext2/uniform2i)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) x, [int](../dart-core/int-class)
y) → void

[uniform2iv](renderingcontext2/uniform2iv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform2iv2](renderingcontext2/uniform2iv2)([UniformLocation](uniformlocation-class)?
location, dynamic v, [int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniform2iv\')
:::

[uniform2ui](renderingcontext2/uniform2ui)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) v0,
[int](../dart-core/int-class) v1) → void

[uniform2uiv](renderingcontext2/uniform2uiv)([UniformLocation](uniformlocation-class)?
location, dynamic v, \[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniform3f](renderingcontext2/uniform3f)([UniformLocation](uniformlocation-class)?
location, [num](../dart-core/num-class) x, [num](../dart-core/num-class)
y, [num](../dart-core/num-class) z) → void

[uniform3fv](renderingcontext2/uniform3fv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform3fv2](renderingcontext2/uniform3fv2)([UniformLocation](uniformlocation-class)?
location, dynamic v, [int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniform3fv\')
:::

[uniform3i](renderingcontext2/uniform3i)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) x, [int](../dart-core/int-class)
y, [int](../dart-core/int-class) z) → void

[uniform3iv](renderingcontext2/uniform3iv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform3iv2](renderingcontext2/uniform3iv2)([UniformLocation](uniformlocation-class)?
location, dynamic v, [int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniform3iv\')
:::

[uniform3ui](renderingcontext2/uniform3ui)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) v0,
[int](../dart-core/int-class) v1, [int](../dart-core/int-class) v2) →
void

[uniform3uiv](renderingcontext2/uniform3uiv)([UniformLocation](uniformlocation-class)?
location, dynamic v, \[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniform4f](renderingcontext2/uniform4f)([UniformLocation](uniformlocation-class)?
location, [num](../dart-core/num-class) x, [num](../dart-core/num-class)
y, [num](../dart-core/num-class) z, [num](../dart-core/num-class) w) →
void

[uniform4fv](renderingcontext2/uniform4fv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform4fv2](renderingcontext2/uniform4fv2)([UniformLocation](uniformlocation-class)?
location, dynamic v, [int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniform4fv\')
:::

[uniform4i](renderingcontext2/uniform4i)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) x, [int](../dart-core/int-class)
y, [int](../dart-core/int-class) z, [int](../dart-core/int-class) w) →
void

[uniform4iv](renderingcontext2/uniform4iv)([UniformLocation](uniformlocation-class)?
location, dynamic v) → void

[uniform4iv2](renderingcontext2/uniform4iv2)([UniformLocation](uniformlocation-class)?
location, dynamic v, [int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniform4iv\')
:::

[uniform4ui](renderingcontext2/uniform4ui)([UniformLocation](uniformlocation-class)?
location, [int](../dart-core/int-class) v0,
[int](../dart-core/int-class) v1, [int](../dart-core/int-class) v2,
[int](../dart-core/int-class) v3) → void

[uniform4uiv](renderingcontext2/uniform4uiv)([UniformLocation](uniformlocation-class)?
location, dynamic v, \[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniformBlockBinding](renderingcontext2/uniformblockbinding)([Program](program-class)
program, [int](../dart-core/int-class) uniformBlockIndex,
[int](../dart-core/int-class) uniformBlockBinding) → void

[uniformMatrix2fv](renderingcontext2/uniformmatrix2fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array) →
void

[uniformMatrix2fv2](renderingcontext2/uniformmatrix2fv2)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array,
[int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniformMatrix2fv\')
:::

[uniformMatrix2x3fv](renderingcontext2/uniformmatrix2x3fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic value,
\[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniformMatrix2x4fv](renderingcontext2/uniformmatrix2x4fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic value,
\[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniformMatrix3fv](renderingcontext2/uniformmatrix3fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array) →
void

[uniformMatrix3fv2](renderingcontext2/uniformmatrix3fv2)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array,
[int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniformMatrix3fv\')
:::

[uniformMatrix3x2fv](renderingcontext2/uniformmatrix3x2fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic value,
\[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniformMatrix3x4fv](renderingcontext2/uniformmatrix3x4fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic value,
\[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniformMatrix4fv](renderingcontext2/uniformmatrix4fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array) →
void

[uniformMatrix4fv2](renderingcontext2/uniformmatrix4fv2)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic array,
[int](../dart-core/int-class) srcOffset,
\[[int](../dart-core/int-class)? srcLength\]) → void

::: {.features}
\@JSName(\'uniformMatrix4fv\')
:::

[uniformMatrix4x2fv](renderingcontext2/uniformmatrix4x2fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic value,
\[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[uniformMatrix4x3fv](renderingcontext2/uniformmatrix4x3fv)([UniformLocation](uniformlocation-class)?
location, [bool](../dart-core/bool-class) transpose, dynamic value,
\[[int](../dart-core/int-class)? srcOffset,
[int](../dart-core/int-class)? srcLength\]) → void

[useProgram](renderingcontext2/useprogram)([Program](program-class)?
program) → void

[validateProgram](renderingcontext2/validateprogram)([Program](program-class)
program) → void

[vertexAttrib1f](renderingcontext2/vertexattrib1f)([int](../dart-core/int-class)
indx, [num](../dart-core/num-class) x) → void

[vertexAttrib1fv](renderingcontext2/vertexattrib1fv)([int](../dart-core/int-class)
indx, dynamic values) → void

[vertexAttrib2f](renderingcontext2/vertexattrib2f)([int](../dart-core/int-class)
indx, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y)
→ void

[vertexAttrib2fv](renderingcontext2/vertexattrib2fv)([int](../dart-core/int-class)
indx, dynamic values) → void

[vertexAttrib3f](renderingcontext2/vertexattrib3f)([int](../dart-core/int-class)
indx, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y,
[num](../dart-core/num-class) z) → void

[vertexAttrib3fv](renderingcontext2/vertexattrib3fv)([int](../dart-core/int-class)
indx, dynamic values) → void

[vertexAttrib4f](renderingcontext2/vertexattrib4f)([int](../dart-core/int-class)
indx, [num](../dart-core/num-class) x, [num](../dart-core/num-class) y,
[num](../dart-core/num-class) z, [num](../dart-core/num-class) w) → void

[vertexAttrib4fv](renderingcontext2/vertexattrib4fv)([int](../dart-core/int-class)
indx, dynamic values) → void

[vertexAttribDivisor](renderingcontext2/vertexattribdivisor)([int](../dart-core/int-class)
index, [int](../dart-core/int-class) divisor) → void

[vertexAttribI4i](renderingcontext2/vertexattribi4i)([int](../dart-core/int-class)
index, [int](../dart-core/int-class) x, [int](../dart-core/int-class) y,
[int](../dart-core/int-class) z, [int](../dart-core/int-class) w) → void

[vertexAttribI4iv](renderingcontext2/vertexattribi4iv)([int](../dart-core/int-class)
index, dynamic v) → void

[vertexAttribI4ui](renderingcontext2/vertexattribi4ui)([int](../dart-core/int-class)
index, [int](../dart-core/int-class) x, [int](../dart-core/int-class) y,
[int](../dart-core/int-class) z, [int](../dart-core/int-class) w) → void

[vertexAttribI4uiv](renderingcontext2/vertexattribi4uiv)([int](../dart-core/int-class)
index, dynamic v) → void

[vertexAttribIPointer](renderingcontext2/vertexattribipointer)([int](../dart-core/int-class)
index, [int](../dart-core/int-class) size, [int](../dart-core/int-class)
type, [int](../dart-core/int-class) stride,
[int](../dart-core/int-class) offset) → void

[vertexAttribPointer](renderingcontext2/vertexattribpointer)([int](../dart-core/int-class)
indx, [int](../dart-core/int-class) size, [int](../dart-core/int-class)
type, [bool](../dart-core/bool-class) normalized,
[int](../dart-core/int-class) stride, [int](../dart-core/int-class)
offset) → void

[viewport](renderingcontext2/viewport)([int](../dart-core/int-class) x,
[int](../dart-core/int-class) y, [int](../dart-core/int-class) width,
[int](../dart-core/int-class) height) → void

[waitSync](renderingcontext2/waitsync)([Sync](sync-class) sync,
[int](../dart-core/int-class) flags, [int](../dart-core/int-class)
timeout) → void

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
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2-class.html>
:::
