[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

Provide a representation of this [double](../double-class) value.

The representation is a number literal such that the closest double
value to the representation\'s mathematical value is this
[double](../double-class).

Returns \"NaN\" for the Not-a-Number value. Returns \"Infinity\" and
\"-Infinity\" for positive and negative Infinity. Returns \"-0.0\" for
negative zero.

For all doubles, `d`, converting to a string and parsing the string back
gives the same value again: `d == double.parse(d.toString())` (except
when `d` is NaN).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/toString.html>
:::
