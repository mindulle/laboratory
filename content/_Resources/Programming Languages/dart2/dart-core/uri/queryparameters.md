[dart:core](../../dart-core/dart-core-library){._links-link}

queryParameters property
========================

::: {#getter .section .multi-line-signature}
[Map](../map-class)\<[String](../string-class),
[String](../string-class)\> queryParameters
:::

The URI query split into a map according to the rules specified for FORM
post in the [HTML 4.01 specification section
17.13.4](https://www.w3.org/TR/REC-html40/interact/forms.html#h-17.13.4 "HTML 4.01 section 17.13.4").

Each key and value in the resulting map has been decoded. If there is no
query, the empty map is returned.

Keys in the query string that have no value are mapped to the empty
string. If a key occurs more than once in the query string, it is mapped
to an arbitrary choice of possible value. The
[queryParametersAll](queryparametersall) getter can provide a map that
maps keys to all of their values.

Example:

``` {.language-dart data-language="dart"}
final uri =
    Uri.parse('https://example.com/api/fetch?limit=10,20,30&max=100');
print(jsonEncode(uri.queryParameters));
// {"limit":"10,20,30","max":"100"}
```

The map is unmodifiable.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<String, String> get queryParameters;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/queryParameters.html>
:::
