[dart:html](../../dart-html/dart-html-library){._links-link}

visibilityState property
========================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) visibilityState

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.FIREFOX)
@SupportedBrowser(SupportedBrowser.IE, '10')
String get visibilityState => JS(
    'String',
    '(#.visibilityState || #.mozVisibilityState || #.msVisibilityState ||'
        '#.webkitVisibilityState)',
    this,
    this,
    this,
    this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/visibilityState.html>
:::
