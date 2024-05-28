[dart:html](../../dart-html/dart-html-library){._links-link}

self property
=============

::: {#getter .section .multi-line-signature}
[WindowBase](../windowbase-class)? self
:::

The current window.

Other resources
---------------

-   [Window.self](https://developer.mozilla.org/en-US/docs/Web/API/Window.self)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
WindowBase? get self => _convertNativeToDart_Window(this._get_self);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/self.html>
:::
