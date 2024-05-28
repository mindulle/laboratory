[dart:html](../../dart-html/dart-html-library){._links-link}

window property
===============

::: {#getter .section .multi-line-signature}
[WindowBase](../windowbase-class)? window
:::

The current window.

Other resources
---------------

-   [Window.window](https://developer.mozilla.org/en-US/docs/Web/API/Window.window)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
WindowBase? get window => _convertNativeToDart_Window(this._get_window);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/window.html>
:::
