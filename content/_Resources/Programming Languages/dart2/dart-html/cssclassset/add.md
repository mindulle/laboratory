[dart:html](../../dart-html/dart-html-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) add(

1.  [String](../../dart-core/string-class) value

)

::: {.features}
override
:::
:::

Add the class `value` to element.

[add](add) and [addAll](addall) are the Dart equivalent of jQuery\'s
[addClass](http://api.jquery.com/addClass/).

If this CssClassSet corresponds to one element. Returns true if `value`
was added to the set, otherwise false.

If this CssClassSet corresponds to many elements, `false` is always
returned.

`value` must be a valid \'token\' representing a single class, i.e. a
non-empty string containing no whitespace. To add multiple classes use
[addAll](addall).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool add(String value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssClassSet/add.html>
:::
