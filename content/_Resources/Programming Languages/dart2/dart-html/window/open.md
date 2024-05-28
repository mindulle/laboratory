[dart:html](../../dart-html/dart-html-library){._links-link}

open method
===========

::: {.section .multi-line-signature}
[WindowBase](../windowbase-class) open(

1.  [String](../../dart-core/string-class) url,
2.  [String](../../dart-core/string-class) name,
3.  \[[String](../../dart-core/string-class)? options\]

)
:::

Opens a new window.

Other resources
---------------

-   [Window.open](https://developer.mozilla.org/en-US/docs/Web/API/Window.open)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
WindowBase open(String url, String name, [String? options]) {
  if (options == null) {
    return _DOMWindowCrossFrame._createSafe(_open2(url, name));
  } else {
    return _DOMWindowCrossFrame._createSafe(_open3(url, name, options));
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/open.html>
:::
