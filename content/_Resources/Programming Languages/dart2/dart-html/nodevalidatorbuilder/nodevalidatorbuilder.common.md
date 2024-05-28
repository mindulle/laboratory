[dart:html](../../dart-html/dart-html-library){._links-link}

NodeValidatorBuilder.common constructor
=======================================

::: {.section .multi-line-signature}
NodeValidatorBuilder.common()
:::

Creates a new NodeValidatorBuilder which accepts common constructs.

By default this will accept HTML5 elements and attributes with the
default [UriPolicy](../uripolicy-class) and templating elements.

Notable syntax which is filtered:

-   Only known-good HTML5 elements and attributes are allowed.
-   All URLs must be same-origin, use [allowNavigation](allownavigation)
    and [allowImages](allowimages) to specify additional URI policies.
-   Inline-styles are not allowed.
-   Custom element tags are disallowed, use
    [allowCustomElement](allowcustomelement).
-   Custom tags extensions are disallowed, use
    [allowTagExtension](allowtagextension).
-   SVG Elements are not allowed, use [allowSvg](allowsvg).

For scenarios where the HTML should only contain formatted text
[allowTextElements](allowtextelements) is more appropriate.

Use [allowSvg](allowsvg) to allow SVG elements.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
NodeValidatorBuilder.common() {
  allowHtml5();
  allowTemplating();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/NodeValidatorBuilder.common.html>
:::
