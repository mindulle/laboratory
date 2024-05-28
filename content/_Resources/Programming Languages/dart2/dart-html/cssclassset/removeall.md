[dart:html](../../dart-html/dart-html-library){._links-link}

removeAll method
================

::: {.section .multi-line-signature}
void removeAll(

1.  [Iterable](../../dart-core/iterable-class)\<[Object](../../dart-core/object-class)?\>
    iterable

)

::: {.features}
override
:::
:::

Remove all classes specified in `iterable` from element.

[remove](remove) and [removeAll](removeall) are the Dart equivalent of
jQuery\'s [removeClass](http://api.jquery.com/removeClass/).

Each element of `iterable` must be a valid \'token\' representing a
single class, i.e. a non-empty string containing no whitespace.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeAll(Iterable<Object?> iterable);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssClassSet/removeAll.html>
:::
