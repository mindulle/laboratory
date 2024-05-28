[dart:html](../../dart-html/dart-html-library){._links-link}

removeAttributeNS method
========================

::: {.section .multi-line-signature}
void removeAttributeNS(

1.  [String](../../dart-core/string-class)? namespaceURI,
2.  [String](../../dart-core/string-class) name

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma('dart2js:tryInline')
void removeAttributeNS(String? namespaceURI, String name) {
  // TODO(41258): Delete this assertion after forcing strong mode.
  // Protect [name] against string conversion to "null" or "undefined".
  assert(name != null, 'Attribute name cannot be null');
  _removeAttributeNS(namespaceURI, name);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/removeAttributeNS.html>
:::
