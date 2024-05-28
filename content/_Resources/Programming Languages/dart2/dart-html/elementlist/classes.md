[dart:html](../../dart-html/dart-html-library){._links-link}

classes property
================

::: {#getter .section .multi-line-signature}
[CssClassSet](../cssclassset-class) classes
:::

The union of all CSS classes applied to the elements in this list.

This set makes it easy to add, remove or toggle (add if not present,
remove if present) the classes applied to a collection of elements.

``` {.language-dart data-language="dart"}
htmlList.classes.add('selected');
htmlList.classes.toggle('isOnline');
htmlList.classes.remove('selected');
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
CssClassSet get classes;
```

::: {#setter .section .multi-line-signature}
void
classes=([Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>
value)
:::

Replace the classes with `value` for every element in this list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set classes(Iterable<String> value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ElementList/classes.html>
:::
