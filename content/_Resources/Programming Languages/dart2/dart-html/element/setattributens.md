[dart:html](../../dart-html/dart-html-library){._links-link}

setAttributeNS method
=====================

::: {.section .multi-line-signature}
void setAttributeNS(

1.  [String](../../dart-core/string-class)? namespaceURI,
2.  [String](../../dart-core/string-class) name,
3.  [Object](../../dart-core/object-class) value

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma('dart2js:tryInline')
void setAttributeNS(String? namespaceURI, String name, Object value) {
  // TODO(41258): Delete these assertions after forcing strong mode.
  // Protect [name] against string conversion to "null" or "undefined".
  assert(name != null, 'Attribute name cannot be null');
  // TODO(sra): assert(value != null, 'Attribute value cannot be null.');
  _setAttributeNS(namespaceURI, name, value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/setAttributeNS.html>
:::
