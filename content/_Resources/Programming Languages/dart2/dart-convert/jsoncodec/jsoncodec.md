[dart:convert](../../dart-convert/dart-convert-library){._links-link}

JsonCodec constructor
=====================

::: {.section .multi-line-signature}
const JsonCodec(

1.  {[Object](../../dart-core/object-class)? reviver(
    1.  [Object](../../dart-core/object-class)? key,
    2.  [Object](../../dart-core/object-class)? value

    )?,
2.  [Object](../../dart-core/object-class)? toEncodable(
    1.  dynamic object

    )?}

)
:::

Creates a `JsonCodec` with the given reviver and encoding function.

The `reviver` function is called during decoding. It is invoked once for
each object or list property that has been parsed. The `key` argument is
either the integer list index for a list property, the string map key
for object properties, or `null` for the final result.

If `reviver` is omitted, it defaults to returning the value argument.

The `toEncodable` function is used during encoding. It is invoked for
values that are not directly encodable to a string (a value that is not
a number, boolean, string, null, list or a map with string keys). The
function must return an object that is directly encodable. The elements
of a returned list and values of a returned map do not need to be
directly encodable, and if they aren\'t, `toEncodable` will be used on
them as well. Please notice that it is possible to cause an infinite
recursive regress in this way, by effectively creating an infinite data
structure through repeated call to `toEncodable`.

If `toEncodable` is omitted, it defaults to a function that returns the
result of calling `.toJson()` on the unencodable object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const JsonCodec(
    {Object? reviver(Object? key, Object? value)?,
    Object? toEncodable(dynamic object)?})
    : _reviver = reviver,
      _toEncodable = toEncodable;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonCodec/JsonCodec.html>
:::
