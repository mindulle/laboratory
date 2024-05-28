[dart:collection](../../dart-collection/dart-collection-library){._links-link}

join method
===========

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) join(

1.  \[[String](../../dart-core/string-class) separator = \"\"\]

)

::: {.features}
inherited
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
  int length = this.length;
  if (!separator.isEmpty) {
    if (length == 0) return "";
    String first = "${elementAt(0)}";
    if (length != this.length) {
      throw ConcurrentModificationError(this);
    }
    StringBuffer buffer = StringBuffer(first);
    for (int i = 1; i < length; i++) {
      buffer.write(separator);
      buffer.write(elementAt(i));
      if (length != this.length) {
        throw ConcurrentModificationError(this);
      }
    }
    return buffer.toString();
  } else {
    StringBuffer buffer = StringBuffer();
    for (int i = 0; i < length; i++) {
      buffer.write(elementAt(i));
      if (length != this.length) {
        throw ConcurrentModificationError(this);
      }
    }
    return buffer.toString();
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/join.html>
:::
