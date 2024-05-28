[dart:html](../../dart-html/dart-html-library){._links-link}

Text constructor
================

::: {.section .multi-line-signature}
Text(

1.  [String](../../dart-core/string-class) data

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Text(String data) => JS(
    'returns:Text;depends:none;effects:none;new:true',
    '#.createTextNode(#)',
    document,
    data);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Text/Text.html>
:::
