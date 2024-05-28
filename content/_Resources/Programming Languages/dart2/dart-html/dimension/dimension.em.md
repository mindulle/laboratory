[dart:html](../../dart-html/dart-html-library){._links-link}

Dimension.em constructor
========================

::: {.section .multi-line-signature}
Dimension.em(

1.  [num](../../dart-core/num-class) \_value

)
:::

Set this CSS Dimension to the specified number of ems.

1em is equal to the current font size. (So 2ems is equal to double the
font size). This is useful for producing website layouts that scale
nicely with the user\'s desired font size.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Dimension.em(this._value) : _unit = 'em';
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Dimension/Dimension.em.html>
:::
