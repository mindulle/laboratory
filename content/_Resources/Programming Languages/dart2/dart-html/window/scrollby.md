[dart:html](../../dart-html/dart-html-library){._links-link}

scrollBy method
===============

::: {.section .multi-line-signature}
void scrollBy(

1.  \[dynamic options\_OR\_x,
2.  dynamic y,
3.  [Map](../../dart-core/map-class)? scrollOptions\]

)
:::

Scrolls the page horizontally and vertically by an offset.

Other resources
---------------

-   [Window.scrollBy](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollBy)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void scrollBy([options_OR_x, y, Map? scrollOptions]) {
  if (options_OR_x == null && y == null && scrollOptions == null) {
    _scrollBy_1();
    return;
  }
  if ((options_OR_x is Map) && y == null && scrollOptions == null) {
    var options_1 = convertDartToNative_Dictionary(options_OR_x);
    _scrollBy_2(options_1);
    return;
  }
  if ((y is num) && (options_OR_x is num) && scrollOptions == null) {
    _scrollBy_3(options_OR_x, y);
    return;
  }
  if ((y is int) && (options_OR_x is int) && scrollOptions == null) {
    _scrollBy_4(options_OR_x, y);
    return;
  }
  if (scrollOptions != null && (y is int) && (options_OR_x is int)) {
    var scrollOptions_1 = convertDartToNative_Dictionary(scrollOptions);
    _scrollBy_5(options_OR_x, y, scrollOptions_1);
    return;
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/scrollBy.html>
:::
