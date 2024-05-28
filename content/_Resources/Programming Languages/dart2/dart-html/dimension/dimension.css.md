[dart:html](../../dart-html/dart-html-library){._links-link}

Dimension.css constructor
=========================

::: {.section .multi-line-signature}
Dimension.css(

1.  [String](../../dart-core/string-class) cssValue

)
:::

Construct a Dimension object from the valid, simple CSS string
`cssValue` that represents a distance measurement.

This constructor is intended as a convenience method for working with
simplistic CSS length measurements. Non-numeric values such as `auto` or
`inherit` or invalid CSS will cause this constructor to throw a
FormatError.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Dimension.css(String cssValue)
    : _unit = '',
      _value = 0 {
  if (cssValue == '') cssValue = '0px';
  if (cssValue.endsWith('%')) {
    _unit = '%';
  } else {
    _unit = cssValue.substring(cssValue.length - 2);
  }
  if (cssValue.contains('.')) {
    _value =
        double.parse(cssValue.substring(0, cssValue.length - _unit.length));
  } else {
    _value = int.parse(cssValue.substring(0, cssValue.length - _unit.length));
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Dimension/Dimension.css.html>
:::
