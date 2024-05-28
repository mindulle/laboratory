[dart:html](../../dart-html/dart-html-library){._links-link}

Element.created constructor
===========================

::: {.section .multi-line-signature}
Element.created()
:::

Custom element creation constructor.

This constructor is used by the DOM when a custom element has been
created. It can only be invoked by subclasses of Element from that
classes created constructor.

``` {.language-dart data-language="dart"}
class CustomElement extends Element {
  factory CustomElement() => new Element.tag('x-custom');

  CustomElement.created() : super.created() {
     // Perform any element initialization.
  }
}
document.registerElement('x-custom', CustomElement);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Element.created() : super._created();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/Element.created.html>
:::
