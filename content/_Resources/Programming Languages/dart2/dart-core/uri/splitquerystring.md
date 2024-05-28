[dart:core](../../dart-core/dart-core-library){._links-link}

splitQueryString method
=======================

::: {.section .multi-line-signature}
[Map](../map-class)\<[String](../string-class),
[String](../string-class)\> splitQueryString(

1.  [String](../string-class) query,
2.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Splits the `query` into a map according to the rules specified for FORM
post in the [HTML 4.01 specification section
17.13.4](https://www.w3.org/TR/REC-html40/interact/forms.html#h-17.13.4 "HTML 4.01 section 17.13.4").

Each key and value in the returned map has been decoded. If the `query`
is the empty string, an empty map is returned.

Keys in the query string that have no value are mapped to the empty
string.

Each query component will be decoded using `encoding`. The default
encoding is UTF-8.

Example:

``` {.language-dart data-language="dart"}
final queryStringMap =
    Uri.splitQueryString('limit=10&max=100&search=Dart%20is%20fun');
print(jsonEncode(queryStringMap));
// {"limit":"10","max":"100","search":"Dart is fun"}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Map<String, String> splitQueryString(String query,
    {Encoding encoding = utf8}) {
  return query.split("&").fold({}, (map, element) {
    int index = element.indexOf("=");
    if (index == -1) {
      if (element != "") {
        map[decodeQueryComponent(element, encoding: encoding)] = "";
      }
    } else if (index != 0) {
      var key = element.substring(0, index);
      var value = element.substring(index + 1);
      map[decodeQueryComponent(key, encoding: encoding)] =
          decodeQueryComponent(value, encoding: encoding);
    }
    return map;
  });
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/splitQueryString.html>
:::
