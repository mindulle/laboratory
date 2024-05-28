[dart:html](../../dart-html/dart-html-library){._links-link}

getContext3d method
===================

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME)
2.  \@SupportedBrowser(SupportedBrowser.FIREFOX)

</div>

[RenderingContext](../../dart-web_gl/renderingcontext-class)?
getContext3d(

1.  {dynamic alpha = true,
2.  dynamic depth = true,
3.  dynamic stencil = false,
4.  dynamic antialias = true,
5.  dynamic premultipliedAlpha = true,
6.  dynamic preserveDrawingBuffer = false}

)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX)
:::
:::

Returns a new Web GL context for this canvas.

Other resources
---------------

-   [WebGL
    fundamentals](http://www.html5rocks.com/en/tutorials/webgl/webgl_fundamentals/)
    from HTML5Rocks.
-   [WebGL homepage](http://get.webgl.org/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.FIREFOX)
gl.RenderingContext? getContext3d(
    {alpha: true,
    depth: true,
    stencil: false,
    antialias: true,
    premultipliedAlpha: true,
    preserveDrawingBuffer: false}) {
  var options = {
    'alpha': alpha,
    'depth': depth,
    'stencil': stencil,
    'antialias': antialias,
    'premultipliedAlpha': premultipliedAlpha,
    'preserveDrawingBuffer': preserveDrawingBuffer,
  };
  var context = getContext('webgl', options);
  if (context == null) {
    context = getContext('experimental-webgl', options);
  }
  return context as gl.RenderingContext?;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasElement/getContext3d.html>
:::
