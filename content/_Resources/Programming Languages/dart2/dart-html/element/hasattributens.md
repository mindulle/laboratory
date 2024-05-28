[dart:html](../../dart-html/dart-html-library){._links-link}

hasAttributeNS method
=====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) hasAttributeNS(

1.  [String](../../dart-core/string-class)? namespaceURI,
2.  [String](../../dart-core/string-class) name

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma('dart2js:tryInline')
bool hasAttributeNS(String? namespaceURI, String name) {
  // TODO(41258): Delete this assertion after forcing strong mode.
  // Protect [name] against string conversion to "null" or "undefined".
  // [namespaceURI] does not need protecting, both `null` and `undefined` map to `null`.
  assert(name != null, 'Attribute name cannot be null');
  return _hasAttributeNS(namespaceURI, name);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/hasAttributeNS.html>
:::
