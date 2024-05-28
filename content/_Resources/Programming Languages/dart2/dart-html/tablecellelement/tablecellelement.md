[dart:html](../../dart-html/dart-html-library){._links-link}

TableCellElement constructor
============================

::: {.section .multi-line-signature}
TableCellElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory TableCellElement() => JS<TableCellElement>(
    'returns:TableCellElement;creates:TableCellElement;new:true',
    '#.createElement(#)',
    document,
    "td");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TableCellElement/TableCellElement.html>
:::
