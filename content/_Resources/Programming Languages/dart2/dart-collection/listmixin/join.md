[dart:collection](../../dart-collection/dart-collection-library){._links-link}

join method
===========

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) join(

1.  \[[String](../../dart-core/string-class) separator = \"\"\]

)

::: {.features}
override
:::
:::

Converts each element to a [String](../../dart-core/string-class) and
concatenates the strings.

Iterates through elements of this iterable, converts each one to a
[String](../../dart-core/string-class) by calling
[Object.toString](../../dart-core/object/tostring), and then
concatenates the strings, with the `separator` string interleaved
between the elements.

Example:

``` {.language-dart data-language="dart"}
final planetsByMass = <double, String>{0.06: 'Mercury', 0.81: 'Venus',
  0.11: 'Mars'};
final joinedNames = planetsByMass.values.join('-'); // Mercury-Venus-Mars
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String join([String separator = ""]) {
  if (length == 0) return "";
  StringBuffer buffer = StringBuffer()..writeAll(this, separator);
  return buffer.toString();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/join.html>
:::
