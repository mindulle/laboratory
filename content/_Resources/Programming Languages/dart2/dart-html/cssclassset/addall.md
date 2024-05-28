[dart:html](../../dart-html/dart-html-library){._links-link}

addAll method
=============

::: {.section .multi-line-signature}
void addAll(

1.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>
    iterable

)

::: {.features}
override
:::
:::

Add all classes specified in `iterable` to element.

[add](add) and [addAll](addall) are the Dart equivalent of jQuery\'s
[addClass](http://api.jquery.com/addClass/).

Each element of `iterable` must be a valid \'token\' representing a
single class, i.e. a non-empty string containing no whitespace.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addAll(Iterable<String> iterable);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssClassSet/addAll.html>
:::
