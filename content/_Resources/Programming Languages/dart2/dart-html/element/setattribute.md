[dart:html](../../dart-html/dart-html-library){._links-link}

setAttribute method
===================

::: {.section .multi-line-signature}
void setAttribute(

1.  [String](../../dart-core/string-class) name,
2.  [Object](../../dart-core/object-class) value

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma('dart2js:tryInline')
void setAttribute(String name, Object value) {
  // TODO(41258): Delete these assertions after forcing strong mode.
  // Protect [name] against string conversion to "null" or "undefined".
  assert(name != null, 'Attribute name cannot be null');
  // TODO(sra): assert(value != null, 'Attribute value cannot be null.');
  _setAttribute(name, value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/setAttribute.html>
:::
