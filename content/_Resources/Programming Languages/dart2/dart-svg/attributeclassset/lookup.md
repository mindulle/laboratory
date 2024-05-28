[dart:svg](../../dart-svg/dart-svg-library){._links-link}

lookup method
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class)? lookup(

1.  [Object](../../dart-core/object-class)? value

)

::: {.features}
inherited
:::
:::

Lookup from the Set interface. Not interesting for a String set.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? lookup(Object? value) => contains(value) ? value as String : null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/lookup.html>
:::
