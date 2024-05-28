[dart:html](../../dart-html/dart-html-library){._links-link}

Element.tag constructor
=======================

::: {.section .multi-line-signature}
Element.tag(

1.  [String](../../dart-core/string-class) tag,
2.  \[[String](../../dart-core/string-class)? typeExtension\]

)
:::

Creates the HTML element specified by the tag name.

This is similar to [Document.createElement](../document/createelement).
`tag` should be a valid HTML tag name. If `tag` is an unknown tag then
this will create an [UnknownElement](../unknownelement-class).

``` {.language-dart data-language="dart"}
var divElement = new Element.tag('div');
print(divElement is DivElement); // 'true'
var myElement = new Element.tag('unknownTag');
print(myElement is UnknownElement); // 'true'
```

For standard elements it is better to use the element type constructors:

``` {.language-dart data-language="dart"}
var element = new DivElement();
```

It is better to use e.g `new CanvasElement()` because the type of the
expression is `CanvasElement`, whereas the type of `Element.tag` is the
less specific `Element`.

See also:

-   [isTagSupported](istagsupported)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Element.tag(String tag, [String? typeExtension]) =>
    _ElementFactoryProvider.createElement_tag(tag, typeExtension);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/Element.tag.html>
:::
