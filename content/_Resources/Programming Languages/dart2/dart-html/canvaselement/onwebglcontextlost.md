[dart:html](../../dart-html/dart-html-library){._links-link}

onWebGlContextLost property
===========================

::: {#getter .section .multi-line-signature}
[ElementStream](../elementstream-class)\<[ContextEvent](../../dart-web_gl/contextevent-class)\>
onWebGlContextLost
:::

Stream of `webglcontextlost` events handled by this
[CanvasElement](../canvaselement-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementStream<gl.ContextEvent> get onWebGlContextLost =>
    webGlContextLostEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasElement/onWebGlContextLost.html>
:::
