[dart:html](../../dart-html/dart-html-library){._links-link}

createShadowRoot method
=======================

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME, \'25\')

</div>

[ShadowRoot](../shadowroot-class) createShadowRoot()

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'25\')
:::
:::

Creates a new shadow root for this shadow host.

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
ShadowRoot createShadowRoot() {
  return JS(
      'ShadowRoot',
      '(#.createShadowRoot || #.webkitCreateShadowRoot).call(#)',
      this,
      this,
      this);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/createShadowRoot.html>
:::
