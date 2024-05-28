[dart:html](../../dart-html/dart-html-library){._links-link}

allowCustomElement method
=========================

::: {.section .multi-line-signature}
void allowCustomElement(

1.  [String](../../dart-core/string-class) tagName,
2.  {[UriPolicy](../uripolicy-class)? uriPolicy,
3.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>?
    attributes,
4.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>?
    uriAttributes}

)
:::

Allow custom elements with the specified tag name and specified
attributes.

This will allow the elements as custom tags (such as ), but will not
allow tag extensions. Use [allowTagExtension](allowtagextension) to
allow tag extensions.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowCustomElement(String tagName,
    {UriPolicy? uriPolicy,
    Iterable<String>? attributes,
    Iterable<String>? uriAttributes}) {
  var tagNameUpper = tagName.toUpperCase();
  var attrs = attributes
      ?.map<String>((name) => '$tagNameUpper::${name.toLowerCase()}');
  var uriAttrs = uriAttributes
      ?.map<String>((name) => '$tagNameUpper::${name.toLowerCase()}');
  if (uriPolicy == null) {
    uriPolicy = new UriPolicy();
  }

  add(new _CustomElementNodeValidator(
      uriPolicy, [tagNameUpper], attrs, uriAttrs, false, true));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowCustomElement.html>
:::
