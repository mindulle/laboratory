[dart:svg](../../dart-svg/dart-svg-library){._links-link}

retainWhere method
==================

::: {.section .multi-line-signature}
void retainWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  [String](../../dart-core/string-class) name

    )

)

::: {.features}
inherited
:::
:::

Removes all elements of this set that fail to satisfy `test`.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
characters.retainWhere(
    (element) => element.startsWith('B') || element.startsWith('C'));
print(characters); // {B, C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void retainWhere(bool test(String name)) {
  modify((s) => s.retainWhere(test));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/retainWhere.html>
:::
