[dart:html](../../dart-html/dart-html-library){._links-link}

performance property
====================

::: {#getter .section .multi-line-signature}
[Performance](../performance-class) performance

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE)
:::
:::

Timing and navigation data for this window.

Other resources
---------------

-   [Measuring page load speed with navigation
    timeing](http://www.html5rocks.com/en/tutorials/webperformance/basics/)
    from HTML5Rocks.
-   [Navigation timing
    specification](http://www.w3.org/TR/navigation-timing/) from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.FIREFOX)
@SupportedBrowser(SupportedBrowser.IE)
Performance get performance native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/performance.html>
:::
