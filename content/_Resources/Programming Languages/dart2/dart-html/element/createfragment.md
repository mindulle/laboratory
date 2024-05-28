[dart:html](../../dart-html/dart-html-library){._links-link}

createFragment method
=====================

::: {.section .multi-line-signature}
[DocumentFragment](../documentfragment-class) createFragment(

1.  [String](../../dart-core/string-class)? html,
2.  {[NodeValidator](../nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)
:::

Create a DocumentFragment from the HTML fragment and ensure that it
follows the sanitization rules specified by the validator or
treeSanitizer.

If the default validation behavior is too restrictive then a new
NodeValidator should be created, either extending or wrapping a default
validator and overriding the validation APIs.

The treeSanitizer is used to walk the generated node tree and sanitize
it. A custom treeSanitizer can also be provided to perform special
validation rules but since the API is more complex to implement this is
discouraged.

The returned tree is guaranteed to only contain nodes and attributes
which are allowed by the provided validator.

See also:

-   [NodeValidator](../nodevalidator-class)
-   [NodeTreeSanitizer](../nodetreesanitizer-class)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DocumentFragment createFragment(String? html,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  if (treeSanitizer == null) {
    if (validator == null) {
      if (_defaultValidator == null) {
        _defaultValidator = new NodeValidatorBuilder.common();
      }
      validator = _defaultValidator;
    }
    if (_defaultSanitizer == null) {
      _defaultSanitizer = new _ValidatingTreeSanitizer(validator!);
    } else {
      _defaultSanitizer!.validator = validator!;
    }
    treeSanitizer = _defaultSanitizer;
  } else if (validator != null) {
    throw new ArgumentError(
        'validator can only be passed if treeSanitizer is null');
  }

  if (_parseDocument == null) {
    _parseDocument = document.implementation!.createHtmlDocument('');
    _parseRange = _parseDocument!.createRange();

    // Workaround for Safari bug. Was also previously Chrome bug 229142
    // - URIs are not resolved in new doc.
    BaseElement base = _parseDocument!.createElement('base') as BaseElement;
    base.href = document.baseUri!;
    _parseDocument!.head!.append(base);
  }

  // TODO(terry): Fixes Chromium 50 change no body after createHtmlDocument()
  if (_parseDocument!.body == null) {
    _parseDocument!.body =
        _parseDocument!.createElement("body") as BodyElement;
  }

  var contextElement;
  if (this is BodyElement) {
    contextElement = _parseDocument!.body!;
  } else {
    contextElement = _parseDocument!.createElement(tagName);
    _parseDocument!.body!.append(contextElement);
  }
  DocumentFragment fragment;
  if (Range.supportsCreateContextualFragment &&
      _canBeUsedToCreateContextualFragment) {
    _parseRange!.selectNodeContents(contextElement);
    // createContextualFragment expects a non-nullable html string.
    // If null is passed, it gets converted to 'null' instead.
    fragment = _parseRange!.createContextualFragment(html ?? 'null');
  } else {
    contextElement._innerHtml = html;

    fragment = _parseDocument!.createDocumentFragment();
    while (contextElement.firstChild != null) {
      fragment.append(contextElement.firstChild);
    }
  }
  if (contextElement != _parseDocument!.body) {
    contextElement.remove();
  }

  treeSanitizer!.sanitizeTree(fragment);
  // Copy the fragment over to the main document (fix for 14184)
  document.adoptNode(fragment);

  return fragment;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/createFragment.html>
:::
