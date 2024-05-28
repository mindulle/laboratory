[dart:html](../../dart-html/dart-html-library){._links-link}

toggleAll method
================

::: {.section .multi-line-signature}
void toggleAll(

1.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>
    iterable,
2.  \[[bool](../../dart-core/bool-class)? shouldAdd\]

)
:::

Toggles all classes specified in `iterable` on element.

Iterate through `iterable`\'s items, and add it if it is not on it, or
remove it if it is. This is the Dart equivalent of jQuery\'s
[toggleClass](http://api.jquery.com/toggleClass/). If `shouldAdd` is
true, then we always add all the classes in `iterable` element. If
`shouldAdd` is false then we always remove all the classes in `iterable`
from the element.

Each element of `iterable` must be a valid \'token\' representing a
single class, i.e. a non-empty string containing no whitespace.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void toggleAll(Iterable<String> iterable, [bool? shouldAdd]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssClassSet/toggleAll.html>
:::
