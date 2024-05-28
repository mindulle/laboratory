[dart:html](../../dart-html/dart-html-library){._links-link}

text property
=============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? text

::: {.features}
\@JSName(\'textContent\')
:::
:::

All text within this node and its descendents.

Other resources
---------------

-   [Node.textContent](https://developer.mozilla.org/en-US/docs/Web/API/Node.textContent)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('textContent')

/**
 * All text within this node and its descendents.
 *
 * ## Other resources
 *
 * * [Node.textContent](https://developer.mozilla.org/en-US/docs/Web/API/Node.textContent)
 *   from MDN.
 */

String? get text native;
```

::: {#setter .section .multi-line-signature}
void text=([String](../../dart-core/string-class)? value)

::: {.features}
\@JSName(\'textContent\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('textContent')
set text(String? value) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/text.html>
:::
