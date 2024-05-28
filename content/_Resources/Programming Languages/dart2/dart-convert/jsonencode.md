[dart:convert](../dart-convert/dart-convert-library){._links-link}

jsonEncode function
===================

::: {.section .multi-line-signature}
[String](../dart-core/string-class) jsonEncode(

1.  [Object](../dart-core/object-class)? object,
2.  {[Object](../dart-core/object-class)? toEncodable(
    1.  [Object](../dart-core/object-class)? nonEncodable

    )?}

)
:::

Converts `object` to a JSON string.

If value contains objects that are not directly encodable to a JSON
string (a value that is not a number, boolean, string, null, list or a
map with string keys), the `toEncodable` function is used to convert it
to an object that must be directly encodable.

If `toEncodable` is omitted, it defaults to a function that returns the
result of calling `.toJson()` on the unencodable object.

Shorthand for `json.encode`. Useful if a local variable shadows the
global [json](json-constant) constant.

Example:

``` {.language-dart data-language="dart"}
const data = {'text': 'foo', 'value': 2, 'status': false, 'extra': null};
final String jsonString = jsonEncode(data);
print(jsonString); // {"text":"foo","value":2,"status":false,"extra":null}
```

Example of converting an otherwise unsupported object to a custom JSON
format:

``` {.language-dart data-language="dart"}
class CustomClass {
  final String text;
  final int value;
  CustomClass({required this.text, required this.value});
  CustomClass.fromJson(Map<String, dynamic> json)
      : text = json['text'],
        value = json['value'];

  static Map<String, dynamic> toJson(CustomClass value) =>
      {'text': value.text, 'value': value.value};
}

void main() {
  final CustomClass cc = CustomClass(text: 'Dart', value: 123);
  final jsonText = jsonEncode({'cc': cc},
      toEncodable: (Object? value) => value is CustomClass
          ? CustomClass.toJson(value)
          : throw UnsupportedError('Cannot convert to JSON: $value'));
  print(jsonText); // {"cc":{"text":"Dart","value":123}}
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String jsonEncode(Object? object,
        {Object? toEncodable(Object? nonEncodable)?}) =>
    json.encode(object, toEncodable: toEncodable);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/jsonEncode.html>
:::
