[dart:svg](../../dart-svg/dart-svg-library){._links-link}

classes property
================

::: {#getter .section .multi-line-signature}
[CssClassSet](../../dart-html/cssclassset-class) classes

::: {.features}
override
:::
:::

The set of CSS classes applied to this element.

This set makes it easy to add, remove or toggle the classes applied to
this element.

``` {.language-dart data-language="dart"}
element.classes.add('selected');
element.classes.toggle('isOnline');
element.classes.remove('selected');
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
CssClassSet get classes => new AttributeClassSet(this);
```

::: {#setter .section .multi-line-signature}
void
classes=([Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>
value)

::: {.features}
inherited
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set classes(Iterable<String> value) {
  // TODO(sra): Do this without reading the classes in clear() and addAll(),
  // or writing the classes in clear().
  CssClassSet classSet = classes;
  classSet.clear();
  classSet.addAll(value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/classes.html>
:::
