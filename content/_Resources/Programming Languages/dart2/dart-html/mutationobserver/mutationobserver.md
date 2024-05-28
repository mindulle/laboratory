[dart:html](../../dart-html/dart-html-library){._links-link}

MutationObserver constructor
============================

::: {.section .multi-line-signature}
MutationObserver(

1.  [MutationCallback](../mutationcallback) callback

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory MutationObserver(MutationCallback callback) {
  // Dummy statement to mark types as instantiated.
  JS('MutationObserver|MutationRecord', '0');

  return JS(
      'MutationObserver',
      'new(window.MutationObserver||window.WebKitMutationObserver||'
          'window.MozMutationObserver)(#)',
      convertDartClosureToJS(_wrapBinaryZone(callback), 2));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MutationObserver/MutationObserver.html>
:::
