[dart:html](../../dart-html/dart-html-library){._links-link}

dir method
==========

::: {.section .multi-line-signature}
void dir(

1.  \[[Object](../../dart-core/object-class)? item,
2.  [Object](../../dart-core/object-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void dir([Object? item, Object? options]) => _isConsoleDefined
    ? JS('void', 'window.console.dir(#, #)', item, options)
    : null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Console/dir.html>
:::
