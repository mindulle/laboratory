[dart:core](../../dart-core/dart-core-library){._links-link}

join method
===========

::: {.section .multi-line-signature}
[String](../string-class) join(

1.  \[[String](../string-class) separator = \"\"\]

)
:::

Converts each element to a [String](../string-class) and concatenates
the strings.

Iterates through elements of this iterable, converts each one to a
[String](../string-class) by calling
[Object.toString](../object/tostring), and then concatenates the
strings, with the `separator` string interleaved between the elements.

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
  Iterator<E> iterator = this.iterator;
  if (!iterator.moveNext()) return "";
  StringBuffer buffer = StringBuffer();
  if (separator == null || separator == "") {
    do {
      buffer.write(iterator.current.toString());
    } while (iterator.moveNext());
  } else {
    buffer.write(iterator.current.toString());
    while (iterator.moveNext()) {
      buffer.write(separator);
      buffer.write(iterator.current.toString());
    }
  }
  return buffer.toString();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/join.html>
:::
