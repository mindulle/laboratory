[dart:core](../../dart-core/dart-core-library){._links-link}

encodeComponent method
======================

::: {.section .multi-line-signature}
[String](../string-class) encodeComponent(

1.  [String](../string-class) component

)
:::

Encode the string `component` using percent-encoding to make it safe for
literal use as a URI component.

All characters except uppercase and lowercase letters, digits and the
characters `-_.!~*'()` are percent-encoded. This is the set of
characters specified in RFC 2396 and which is specified for the
encodeUriComponent in ECMA-262 version 5.1.

When manually encoding path segments or query components, remember to
encode each part separately before building the path or query string.

For encoding the query part consider using
[encodeQueryComponent](encodequerycomponent).

To avoid the need for explicitly encoding, use the
[pathSegments](pathsegments) and [queryParameters](queryparameters)
optional named arguments when constructing a [Uri](../uri-class).

Example:

``` {.language-dart data-language="dart"}
const request = 'http://example.com/search=Dart';
final encoded = Uri.encodeComponent(request);
print(encoded); // http%3A%2F%2Fexample.com%2Fsearch%3DDart
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String encodeComponent(String component) {
  return _Uri._uriEncode(_Uri._unreserved2396Table, component, utf8, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/encodeComponent.html>
:::
