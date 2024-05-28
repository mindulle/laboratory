[dart:html](../../dart-html/dart-html-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) remove(

1.  [Object](../../dart-core/object-class)? value

)

::: {.features}
override
:::
:::

Remove the class `value` from element, and return true on successful
removal.

[remove](remove) and [removeAll](removeall) are the Dart equivalent of
jQuery\'s [removeClass](http://api.jquery.com/removeClass/).

`value` must be a valid \'token\' representing a single class, i.e. a
non-empty string containing no whitespace. To remove multiple classes,
use [removeAll](removeall).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool remove(Object? value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssClassSet/remove.html>
:::
