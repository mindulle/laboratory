[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
dynamic convert(

1.  [String](../../dart-core/string-class) input

)

::: {.features}
override
:::
:::

Converts the given JSON-string `input` to its corresponding object.

Parsed JSON values are of the types [num](../../dart-core/num-class),
[String](../../dart-core/string-class),
[bool](../../dart-core/bool-class), [Null](../../dart-core/null-class),
[List](../../dart-core/list-class)s of parsed JSON values or
[Map](../../dart-core/map-class)s from
[String](../../dart-core/string-class) to parsed JSON values.

If `this` was initialized with a reviver, then the parsing operation
invokes the reviver on every object or list property that has been
parsed. The arguments are the property name
([String](../../dart-core/string-class)) or list index
([int](../../dart-core/int-class)), and the value is the parsed value.
The return value of the reviver is used as the value of that property
instead the parsed value.

Throws [FormatException](../../dart-core/formatexception-class) if the
input is not valid JSON text.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
dynamic convert(String input) => _parseJson(input, _reviver);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonDecoder/convert.html>
:::
