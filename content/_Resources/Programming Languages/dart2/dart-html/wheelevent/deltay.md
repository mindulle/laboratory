[dart:html](../../dart-html/dart-html-library){._links-link}

deltaY property
===============

::: {#getter .section .multi-line-signature}
[num](../../dart-core/num-class) deltaY
:::

The amount that is expected to scroll vertically, in units determined by
[deltaMode](deltamode).

See also:

-   [WheelEvent.deltaY](http://dev.w3.org/2006/webapi/DOM-Level-3-Events/html/DOM3-Events.html#events-WheelEvent-deltaY)
    from the W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
num get deltaY {
  // deltaY may be missing or undefined.
  num? value = JS('', '#.deltaY', this);
  if (value != null) return value;
  throw new UnsupportedError('deltaY is not supported');
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WheelEvent/deltaY.html>
:::
