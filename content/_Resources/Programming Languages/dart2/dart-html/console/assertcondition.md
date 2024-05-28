[dart:html](../../dart-html/dart-html-library){._links-link}

assertCondition method
======================

::: {.section .multi-line-signature}
void assertCondition(

1.  \[[bool](../../dart-core/bool-class)? condition,
2.  [Object](../../dart-core/object-class)? arg\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void assertCondition([bool? condition, Object? arg]) => _isConsoleDefined
    ? JS('void', 'window.console.assert(#, #)', condition, arg)
    : null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Console/assertCondition.html>
:::
