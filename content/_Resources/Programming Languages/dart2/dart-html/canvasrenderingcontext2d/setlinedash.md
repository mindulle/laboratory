[dart:html](../../dart-html/dart-html-library){._links-link}

setLineDash method
==================

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME)
2.  \@SupportedBrowser(SupportedBrowser.SAFARI)
3.  \@SupportedBrowser(SupportedBrowser.IE, \'11\')
4.  \@Unstable()

</div>

void setLineDash(

1.  [List](../../dart-core/list-class)\<[num](../../dart-core/num-class)\>
    dash

)

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
void setLineDash(List<num> dash) {
  // TODO(14316): Firefox has this functionality with mozDash, but it's a bit
  // different.
  if (JS('bool', '!!#.setLineDash', this)) {
    JS('void', '#.setLineDash(#)', this, dash);
  } else if (JS('bool', '!!#.webkitLineDash', this)) {
    JS('void', '#.webkitLineDash = #', this, dash);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/setLineDash.html>
:::
