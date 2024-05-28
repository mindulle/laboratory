[dart:core](../../dart-core/dart-core-library){._links-link}

tryParse method
===============

::: {.section .multi-line-signature}
[DateTime](../datetime-class)? tryParse(

1.  [String](../string-class) formattedString

)
:::

Constructs a new [DateTime](../datetime-class) instance based on
`formattedString`.

Works like [parse](parse) except that this function returns `null` where
[parse](parse) would throw a
[FormatException](../formatexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static DateTime? tryParse(String formattedString) {
  // TODO: Optimize to avoid throwing.
  try {
    return parse(formattedString);
  } on FormatException {
    return null;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/tryParse.html>
:::
