[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) convert(

1.  [Object](../../dart-core/object-class)? object

)

::: {.features}
override
:::
:::

Converts `object` to a JSON [String](../../dart-core/string-class).

Directly serializable values are [num](../../dart-core/num-class),
[String](../../dart-core/string-class),
[bool](../../dart-core/bool-class), and
[Null](../../dart-core/null-class), as well as some
[List](../../dart-core/list-class) and [Map](../../dart-core/map-class)
values. For [List](../../dart-core/list-class), the elements must all be
serializable. For [Map](../../dart-core/map-class), the keys must be
[String](../../dart-core/string-class) and the values must be
serializable.

If a value of any other type is attempted to be serialized, the
`toEncodable` function provided in the constructor is called with the
value as argument. The result, which must be a directly serializable
value, is serialized instead of the original value.

If the conversion throws, or returns a value that is not directly
serializable, a
[JsonUnsupportedObjectError](../jsonunsupportedobjecterror-class)
exception is thrown. If the call throws, the error is caught and stored
in the
[JsonUnsupportedObjectError](../jsonunsupportedobjecterror-class)\'s
`cause` field.

If a [List](../../dart-core/list-class) or
[Map](../../dart-core/map-class) contains a reference to itself,
directly or through other lists or maps, it cannot be serialized and a
[JsonCyclicError](../jsoncyclicerror-class) is thrown.

`object` should not change during serialization.

If an object is serialized more than once, [convert](convert) may cache
the text for it. In other words, if the content of an object changes
after it is first serialized, the new values may not be reflected in the
result.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String convert(Object? object) =>
    _JsonStringStringifier.stringify(object, _toEncodable, indent);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonEncoder/convert.html>
:::
