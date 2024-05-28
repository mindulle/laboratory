[dart:html](../../dart-html/dart-html-library){._links-link}

animationFrame property
=======================

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class)\<[num](../../dart-core/num-class)\>
animationFrame
:::

Returns a Future that completes just before the window is about to
repaint so the user can draw an animation frame.

If you need to later cancel this animation, use
[requestAnimationFrame](requestanimationframe) instead.

The [Future](../../dart-async/future-class) completes to a timestamp
that represents a floating point value of the number of milliseconds
that have elapsed since the page started to load (which is also the
timestamp at this call to animationFrame).

Note: The code that runs when the future completes should call
[animationFrame](animationframe) again for the animation to continue.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<num> get animationFrame {
  var completer = new Completer<num>.sync();
  requestAnimationFrame((time) {
    completer.complete(time);
  });
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/animationFrame.html>
:::
