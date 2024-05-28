[dart:html](../../dart-html/dart-html-library){._links-link}

path property
=============

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[Node](../node-class)\> path

::: {.features}
inherited
:::
:::

This event\'s path, taking into account shadow DOM.

Other resources
---------------

-   [Shadow DOM extensions to
    Event](http://w3c.github.io/webcomponents/spec/shadow/#extensions-to-event)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// https://dvcs.w3.org/hg/webcomponents/raw-file/tip/spec/shadow/index.html#extensions-to-event
List<Node> get path => wrapped.path as List<Node>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyEvent/path.html>
:::
