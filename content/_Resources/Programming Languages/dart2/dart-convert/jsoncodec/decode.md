[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decode method
=============

::: {.section .multi-line-signature}
dynamic decode(

1.  [String](../../dart-core/string-class) source,
2.  {[Object](../../dart-core/object-class)? reviver(
    1.  [Object](../../dart-core/object-class)? key,
    2.  [Object](../../dart-core/object-class)? value

    )?}

)

::: {.features}
override
:::
:::

Parses the string and returns the resulting Json object.

The optional `reviver` function is called once for each object or list
property that has been parsed during decoding. The `key` argument is
either the integer list index for a list property, the string map key
for object properties, or `null` for the final result.

The default `reviver` (when not provided) is the identity function.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
dynamic decode(String source,
    {Object? reviver(Object? key, Object? value)?}) {
  reviver ??= _reviver;
  if (reviver == null) return decoder.convert(source);
  return JsonDecoder(reviver).convert(source);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonCodec/decode.html>
:::
