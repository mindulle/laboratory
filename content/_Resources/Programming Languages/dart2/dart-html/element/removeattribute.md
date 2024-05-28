[dart:html](../../dart-html/dart-html-library){._links-link}

removeAttribute method
======================

::: {.section .multi-line-signature}
void removeAttribute(

1.  [String](../../dart-core/string-class) name

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma('dart2js:tryInline')
void removeAttribute(String name) {
  // TODO(41258): Delete this assertion after forcing strong mode.
  // Protect [name] against string conversion to "null" or "undefined".
  assert(name != null, 'Attribute name cannot be null');
  _removeAttribute(name);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/removeAttribute.html>
:::
