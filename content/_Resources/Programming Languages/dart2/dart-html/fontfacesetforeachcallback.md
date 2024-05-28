[dart:html](../dart-html/dart-html-library){._links-link}

FontFaceSetForEachCallback typedef
==================================

::: {.section .multi-line-signature}
FontFaceSetForEachCallback = void Function([FontFace](fontface-class)
fontFace, [FontFace](fontface-class) fontFaceAgain,
[FontFaceSet](fontfaceset-class) set)
:::

Emitted for any setlike IDL entry needs a callback signature. Today
there is only one.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef void FontFaceSetForEachCallback(
    FontFace fontFace, FontFace fontFaceAgain, FontFaceSet set);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FontFaceSetForEachCallback.html>
:::
