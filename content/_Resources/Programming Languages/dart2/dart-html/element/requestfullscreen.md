[dart:html](../../dart-html/dart-html-library){._links-link}

requestFullscreen method
========================

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME)
2.  \@SupportedBrowser(SupportedBrowser.FIREFOX)
3.  \@SupportedBrowser(SupportedBrowser.SAFARI)

</div>

[Future](../../dart-async/future-class)\<void\> requestFullscreen(

1.  \[[Map](../../dart-core/map-class)? options\]

)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::
:::

Displays this element fullscreen.

Other resources
---------------

-   [Fullscreen
    API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API)
    from MDN.
-   [Fullscreen specification](http://www.w3.org/TR/fullscreen/) from
    W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.FIREFOX)
@SupportedBrowser(SupportedBrowser.SAFARI)
Future<void> requestFullscreen([Map? options]) {
  var retValue;
  if (options != null) {
    retValue = JS(
        '',
        '(#.requestFullscreen||#.webkitRequestFullscreen).call(#, #)',
        this,
        this,
        this,
        convertDartToNative_Dictionary(options));
  } else {
    retValue = JS(
        '',
        '(#.requestFullscreen||#.webkitRequestFullscreen).call(#)',
        this,
        this,
        this);
  }
  if (retValue != null) return promiseToFuture(retValue);
  return Future<void>.value();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/requestFullscreen.html>
:::
