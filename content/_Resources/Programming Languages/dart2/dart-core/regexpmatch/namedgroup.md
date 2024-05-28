[dart:core](../../dart-core/dart-core-library){._links-link}

namedGroup method
=================

::: {.section .multi-line-signature}
[String](../string-class)? namedGroup(

1.  [String](../string-class) name

)
:::

The string matched by the group named `name`.

Returns the string matched by the capture group named `name`, or `null`
if no string was matched by that capture group as part of this match.

The `name` must be the name of a named capture group in the regular
expression creating this match (that is, the name must be in
[groupNames](groupnames)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? namedGroup(String name);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExpMatch/namedGroup.html>
:::
