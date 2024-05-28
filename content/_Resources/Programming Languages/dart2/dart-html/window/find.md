[dart:html](../../dart-html/dart-html-library){._links-link}

find method
===========

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) find(

1.  [String](../../dart-core/string-class)? string,
2.  [bool](../../dart-core/bool-class)? caseSensitive,
3.  [bool](../../dart-core/bool-class)? backwards,
4.  [bool](../../dart-core/bool-class)? wrap,
5.  [bool](../../dart-core/bool-class)? wholeWord,
6.  [bool](../../dart-core/bool-class)? searchInFrames,
7.  [bool](../../dart-core/bool-class)? showDialog

)
:::

Finds text in this window.

Other resources
---------------

-   [Window.find](https://developer.mozilla.org/en-US/docs/Web/API/Window.find)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool find(String? string, bool? caseSensitive, bool? backwards, bool? wrap,
    bool? wholeWord, bool? searchInFrames, bool? showDialog) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/find.html>
:::
