[dart:html](../../dart-html/dart-html-library){._links-link}

shadowRoot property
===================

::: {#getter .section .multi-line-signature}
[ShadowRoot](../shadowroot-class)? shadowRoot

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'25\')
:::
:::

The shadow root of this shadow host.

Other resources
---------------

-   [Shadow DOM
    101](http://www.html5rocks.com/en/tutorials/webcomponents/shadowdom/)
    from HTML5Rocks.
-   [Shadow DOM specification](http://www.w3.org/TR/shadow-dom/) from
    W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME, '25')
ShadowRoot? get shadowRoot =>
    JS('ShadowRoot|Null', '#.shadowRoot || #.webkitShadowRoot', this, this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/shadowRoot.html>
:::
