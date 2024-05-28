[dart:html](../../dart-html/dart-html-library){._links-link}

requestAnimationFrame method
============================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) requestAnimationFrame(

1.  [FrameRequestCallback](../framerequestcallback) callback

)
:::

Called to draw an animation frame and then request the window to repaint
after `callback` has finished (creating the animation).

Use this method only if you need to later call
[cancelAnimationFrame](cancelanimationframe). If not, the preferred Dart
idiom is to set animation frames by calling
[animationFrame](animationframe), which returns a Future.

Returns a non-zero valued integer to represent the request id for this
request. This value only needs to be saved if you intend to call
[cancelAnimationFrame](cancelanimationframe) so you can specify the
particular animation to cancel.

Note: The supplied `callback` needs to call
[requestAnimationFrame](requestanimationframe) again for the animation
to continue.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int requestAnimationFrame(FrameRequestCallback callback) {
  _ensureRequestAnimationFrame();
  return _requestAnimationFrame(_wrapZone(callback)!);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/requestAnimationFrame.html>
:::
