[dart:html](../../dart-html/dart-html-library){._links-link}

parent property
===============

::: {#getter .section .multi-line-signature}
[WindowBase](../windowbase-class)? parent

::: {.features}
override
:::
:::

A reference to the parent of this window.

If this [WindowBase](../windowbase-class) has no parent,
[parent](parent) will return a reference to the
[WindowBase](../windowbase-class) itself.

``` {.language-dart data-language="dart"}
IFrameElement myIFrame = new IFrameElement();
window.document.body.elements.add(myIFrame);
print(myIframe.contentWindow.parent == window) // 'true'

print(window.parent == window) // 'true'
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
WindowBase? get parent => _convertNativeToDart_Window(this._get_parent);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/parent.html>
:::
