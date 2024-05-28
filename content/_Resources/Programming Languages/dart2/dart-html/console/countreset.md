[dart:html](../../dart-html/dart-html-library){._links-link}

countReset method
=================

::: {.section .multi-line-signature}
void countReset(

1.  \[[String](../../dart-core/string-class)? arg\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void countReset([String? arg]) => _isConsoleDefined
    ? JS('void', 'window.console.countReset(#)', arg)
    : null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Console/countReset.html>
:::
