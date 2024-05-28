[dart:html](../../dart-html/dart-html-library){._links-link}

observe method
==============

::: {.section .multi-line-signature}
void observe(

1.  [Node](../node-class) target,
2.  {[bool](../../dart-core/bool-class)? childList,
3.  [bool](../../dart-core/bool-class)? attributes,
4.  [bool](../../dart-core/bool-class)? characterData,
5.  [bool](../../dart-core/bool-class)? subtree,
6.  [bool](../../dart-core/bool-class)? attributeOldValue,
7.  [bool](../../dart-core/bool-class)? characterDataOldValue,
8.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
    attributeFilter}

)
:::

Observes the target for the specified changes.

Some requirements for the optional parameters:

-   Either childList, attributes or characterData must be true.
-   If attributeOldValue is true then attributes must also be true.
-   If attributeFilter is specified then attributes must be true.
-   If characterDataOldValue is true then characterData must be true.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void observe(Node target,
    {bool? childList,
    bool? attributes,
    bool? characterData,
    bool? subtree,
    bool? attributeOldValue,
    bool? characterDataOldValue,
    List<String>? attributeFilter}) {
  // Parse options into map of known type.
  var parsedOptions = _createDict();

  // Override options passed in the map with named optional arguments.
  override(key, value) {
    if (value != null) _add(parsedOptions, key, value);
  }

  override('childList', childList);
  override('attributes', attributes);
  override('characterData', characterData);
  override('subtree', subtree);
  override('attributeOldValue', attributeOldValue);
  override('characterDataOldValue', characterDataOldValue);
  if (attributeFilter != null) {
    override('attributeFilter', _fixupList(attributeFilter));
  }

  _call(target, parsedOptions);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MutationObserver/observe.html>
:::
