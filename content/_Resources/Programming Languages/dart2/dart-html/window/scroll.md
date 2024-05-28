[dart:html](../../dart-html/dart-html-library){._links-link}

scroll method
=============

::: {.section .multi-line-signature}
void scroll(

1.  \[dynamic options\_OR\_x,
2.  dynamic y,
3.  [Map](../../dart-core/map-class)? scrollOptions\]

)
:::

Scrolls the page horizontally and vertically to a specific point.

This method is identical to [scrollTo](scrollto).

Other resources
---------------

-   [Window.scroll](https://developer.mozilla.org/en-US/docs/Web/API/Window/scroll)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void scroll([options_OR_x, y, Map? scrollOptions]) {
  if (options_OR_x == null && y == null && scrollOptions == null) {
    _scroll_1();
    return;
  }
  if ((options_OR_x is Map) && y == null && scrollOptions == null) {
    var options_1 = convertDartToNative_Dictionary(options_OR_x);
    _scroll_2(options_1);
    return;
  }
  if ((y is num) && (options_OR_x is num) && scrollOptions == null) {
    _scroll_3(options_OR_x, y);
    return;
  }
  if ((y is int) && (options_OR_x is int) && scrollOptions == null) {
    _scroll_4(options_OR_x, y);
    return;
  }
  if (scrollOptions != null && (y is int) && (options_OR_x is int)) {
    var scrollOptions_1 = convertDartToNative_Dictionary(scrollOptions);
    _scroll_5(options_OR_x, y, scrollOptions_1);
    return;
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/scroll.html>
:::
