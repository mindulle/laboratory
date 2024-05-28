[dart:html](../../dart-html/dart-html-library){._links-link}

lineDashOffset property
=======================

::: {#getter .section .multi-line-signature}
[num](../../dart-core/num-class) lineDashOffset

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI),
\@SupportedBrowser(SupportedBrowser.IE, \'11\'), \@Unstable()
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.SAFARI)
@SupportedBrowser(SupportedBrowser.IE, '11')
@Unstable()
// TODO(14316): Firefox has this functionality with mozDashOffset, but it
// needs to be polyfilled.
num get lineDashOffset =>
    JS('num', '#.lineDashOffset || #.webkitLineDashOffset', this, this);
```

::: {#setter .section .multi-line-signature}
void lineDashOffset=([num](../../dart-core/num-class) value)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI),
\@SupportedBrowser(SupportedBrowser.IE, \'11\'), \@Unstable()
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.SAFARI)
@SupportedBrowser(SupportedBrowser.IE, '11')
@Unstable()
// TODO(14316): Firefox has this functionality with mozDashOffset, but it
// needs to be polyfilled.
set lineDashOffset(num value) {
  JS(
      'void',
      'typeof #.lineDashOffset != "undefined" ? #.lineDashOffset = # : '
          '#.webkitLineDashOffset = #',
      this,
      this,
      value,
      this,
      value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/lineDashOffset.html>
:::
