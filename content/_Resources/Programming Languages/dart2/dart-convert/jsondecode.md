[dart:convert](../dart-convert/dart-convert-library){._links-link}

jsonDecode function
===================

::: {.section .multi-line-signature}
dynamic jsonDecode(

1.  [String](../dart-core/string-class) source,
2.  {[Object](../dart-core/object-class)? reviver(
    1.  [Object](../dart-core/object-class)? key,
    2.  [Object](../dart-core/object-class)? value

    )?}

)
:::

Parses the string and returns the resulting Json object.

The optional `reviver` function is called once for each object or list
property that has been parsed during decoding. The `key` argument is
either the integer list index for a list property, the string map key
for object properties, or `null` for the final result.

The default `reviver` (when not provided) is the identity function.

Shorthand for `json.decode`. Useful if a local variable shadows the
global [json](json-constant) constant.

Example:

``` {.language-dart data-language="dart"}
const jsonString =
    '{"text": "foo", "value": 1, "status": false, "extra": null}';

final data = jsonDecode(jsonString);
print(data['text']); // foo
print(data['value']); // 1
print(data['status']); // false
print(data['extra']); // null

const jsonArray = '''
  [{"text": "foo", "value": 1, "status": true},
   {"text": "bar", "value": 2, "status": false}]
''';

final List<dynamic> dataList = jsonDecode(jsonArray);
print(dataList[0]); // {text: foo, value: 1, status: true}
print(dataList[1]); // {text: bar, value: 2, status: false}

final item = dataList[0];
print(item['text']); // foo
print(item['value']); // 1
print(item['status']); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
dynamic jsonDecode(String source,
        {Object? reviver(Object? key, Object? value)?}) =>
    json.decode(source, reviver: reviver);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/jsonDecode.html>
:::
