[dart:core](../../dart-core/dart-core-library){._links-link}

name property
=============

::: {#getter .section .multi-line-signature}
[String](../string-class) name
:::

The name of the enum value.

The name is a string containing the source identifier used to declare
the enum value.

For example, given a declaration like:

``` {.language-dart data-language="dart"}
enum MyEnum {
  value1,
  value2
}
```

the result of `MyEnum.value1.name` is the string `"value1"`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get name => _name;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/EnumName/name.html>
:::
