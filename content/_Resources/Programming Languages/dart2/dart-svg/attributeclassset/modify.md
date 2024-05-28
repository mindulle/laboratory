[dart:svg](../../dart-svg/dart-svg-library){._links-link}

modify method
=============

::: {.section .multi-line-signature}
dynamic modify(

1.  dynamic f(
    1.  [Set](../../dart-core/set-class)\<[String](../../dart-core/string-class)\>
        s

    )

)

::: {.features}
inherited
:::
:::

Helper method used to modify the set of css classes on this element.

f - callback with: s - a Set of all the css class name currently on this
element.

After f returns, the modified set is written to the className property
of this element.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
modify(f(Set<String> s)) {
  Set<String> s = readClasses();
  var ret = f(s);
  writeClasses(s);
  return ret;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/modify.html>
:::
