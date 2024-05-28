[dart:html](../../dart-html/dart-html-library){._links-link}

allowTagExtension method
========================

::: {.section .multi-line-signature}
void allowTagExtension(

1.  [String](../../dart-core/string-class) tagName,
2.  [String](../../dart-core/string-class) baseName,
3.  {[UriPolicy](../uripolicy-class)? uriPolicy,
4.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>?
    attributes,
5.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>?
    uriAttributes}

)
:::

Allow custom tag extensions with the specified type name and specified
attributes.

This will allow tag extensions (such as

), but will not allow custom tags. Use
[allowCustomElement](allowcustomelement) to allow custom tags.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowTagExtension(String tagName, String baseName,
    {UriPolicy? uriPolicy,
    Iterable<String>? attributes,
    Iterable<String>? uriAttributes}) {
  var baseNameUpper = baseName.toUpperCase();
  var tagNameUpper = tagName.toUpperCase();
  var attrs = attributes
      ?.map<String>((name) => '$baseNameUpper::${name.toLowerCase()}');
  var uriAttrs = uriAttributes
      ?.map<String>((name) => '$baseNameUpper::${name.toLowerCase()}');
  if (uriPolicy == null) {
    uriPolicy = new UriPolicy();
  }

  add(new _CustomElementNodeValidator(uriPolicy,
      [tagNameUpper, baseNameUpper], attrs, uriAttrs, true, false));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowTagExtension.html>
:::
