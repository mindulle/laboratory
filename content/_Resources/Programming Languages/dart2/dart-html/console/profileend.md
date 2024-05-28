[dart:html](../../dart-html/dart-html-library){._links-link}

profileEnd method
=================

::: {.section .multi-line-signature}
void profileEnd(

1.  \[[String](../../dart-core/string-class)? title\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void profileEnd([String? title]) => _isConsoleDefined
    ? JS('void', 'window.console.profileEnd(#)', title)
    : null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Console/profileEnd.html>
:::
