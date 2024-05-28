[dart:convert](../../dart-convert/dart-convert-library){._links-link}

getByName method
================

::: {.section .multi-line-signature}
[Encoding](../encoding-class)? getByName(

1.  [String](../../dart-core/string-class)? name

)
:::

Returns an [Encoding](../encoding-class) for a named character set.

The names used are the IANA official names for the character set (see
[IANA character
sets](http://www.iana.org/assignments/character-sets/character-sets.xml)).
The names are case insensitive.

If character set is not supported `null` is returned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Encoding? getByName(String? name) {
  if (name == null) return null;
  return _nameToEncoding[name.toLowerCase()];
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Encoding/getByName.html>
:::
