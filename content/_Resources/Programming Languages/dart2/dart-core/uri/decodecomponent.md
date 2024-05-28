[dart:core](../../dart-core/dart-core-library){._links-link}

decodeComponent method
======================

::: {.section .multi-line-signature}
[String](../string-class) decodeComponent(

1.  [String](../string-class) encodedComponent

)
:::

Decodes the percent-encoding in `encodedComponent`.

Note that decoding a URI component might change its meaning as some of
the decoded characters could be characters which are delimiters for a
given URI component type. Always split a URI component using the
delimiters for the component before decoding the individual parts.

For handling the [path](path) and [query](query) components, consider
using [pathSegments](pathsegments) and
[queryParameters](queryparameters) to get the separated and decoded
component.

Example:

``` {.language-dart data-language="dart"}
final decoded =
    Uri.decodeComponent('http%3A%2F%2Fexample.com%2Fsearch%3DDart');
print(decoded); // http://example.com/search=Dart
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String decodeComponent(String encodedComponent) {
  return _Uri._uriDecode(
      encodedComponent, 0, encodedComponent.length, utf8, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/decodeComponent.html>
:::
