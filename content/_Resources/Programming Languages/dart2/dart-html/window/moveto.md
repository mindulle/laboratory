[dart:html](../../dart-html/dart-html-library){._links-link}

moveTo method
=============

::: {.section .multi-line-signature}
void moveTo(

1.  [Point](../../dart-math/point-class)\<[num](../../dart-core/num-class)\>
    p

)
:::

Moves this window to a specific position.

x and y can be negative.

Other resources
---------------

-   [Window.moveTo](https://developer.mozilla.org/en-US/docs/Web/API/Window.moveTo)
    from MDN.
-   [Window.moveTo](http://dev.w3.org/csswg/cssom-view/#dom-window-moveto)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void moveTo(Point p) {
  _moveTo(p.x.toInt(), p.y.toInt());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/moveTo.html>
:::
