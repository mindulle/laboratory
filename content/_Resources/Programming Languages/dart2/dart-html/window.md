[dart:html](../dart-html/dart-html-library){._links-link}

window top-level property
=========================

::: {#getter .section .multi-line-signature}
[Window](window-class) window
:::

Top-level container for a web page, which is usually a browser tab or
window.

Each web page loaded in the browser has its own [Window](window-class),
which is a container for the web page.

If the web page has any `<iframe>` elements, then each `<iframe>` has
its own [Window](window-class) object, which is accessible only to that
`<iframe>`.

See also:

-   [Window](https://developer.mozilla.org/en-US/docs/Web/API/window)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Window get window => JS('Window', 'window');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/window.html>
:::
