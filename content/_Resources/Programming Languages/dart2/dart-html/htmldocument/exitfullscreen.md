[dart:html](../../dart-html/dart-html-library){._links-link}

exitFullscreen method
=====================

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME)
2.  \@SupportedBrowser(SupportedBrowser.SAFARI)

</div>

void exitFullscreen()

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI), override
:::
:::

Returns page to standard layout.

Has no effect if the page is not in fullscreen mode.

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
@SupportedBrowser(SupportedBrowser.SAFARI)
void exitFullscreen() {
  _webkitExitFullscreen();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HtmlDocument/exitFullscreen.html>
:::
