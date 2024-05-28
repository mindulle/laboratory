[dart:html](../../dart-html/dart-html-library){._links-link}

time method
===========

::: {.section .multi-line-signature}
void time(

1.  \[[String](../../dart-core/string-class)? label\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void time([String? label]) =>
    _isConsoleDefined ? JS('void', 'window.console.time(#)', label) : null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Console/time.html>
:::
