[dart:html](../../dart-html/dart-html-library){._links-link}

pushState method
================

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME)
2.  \@SupportedBrowser(SupportedBrowser.FIREFOX)
3.  \@SupportedBrowser(SupportedBrowser.IE, \'10\')
4.  \@SupportedBrowser(SupportedBrowser.SAFARI)

</div>

void pushState(

1.  dynamic data,
2.  [String](../../dart-core/string-class) title,
3.  [String](../../dart-core/string-class)? url

)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.FIREFOX)
@SupportedBrowser(SupportedBrowser.IE, '10')
@SupportedBrowser(SupportedBrowser.SAFARI)
void pushState(/*SerializedScriptValue*/ data, String title, String? url) {
  var data_1 = convertDartToNative_SerializedScriptValue(data);
  _pushState_1(data_1, title, url);
  return;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/History/pushState.html>
:::
