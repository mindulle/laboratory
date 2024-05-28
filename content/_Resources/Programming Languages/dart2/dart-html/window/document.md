[dart:html](../../dart-html/dart-html-library){._links-link}

document property
=================

::: {#getter .section .multi-line-signature}
[Document](../document-class) document
:::

The newest document in this window.

Other resources
---------------

-   [Loading web
    pages](https://html.spec.whatwg.org/multipage/browsers.html) from
    WHATWG.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Document get document => JS('Document', '#.document', this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/document.html>
:::
