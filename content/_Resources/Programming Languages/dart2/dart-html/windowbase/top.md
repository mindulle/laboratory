[dart:html](../../dart-html/dart-html-library){._links-link}

top property
============

::: {#getter .section .multi-line-signature}
[WindowBase](../windowbase-class)? top
:::

A reference to the topmost window in the window hierarchy.

If this [WindowBase](../windowbase-class) is the topmost
[WindowBase](../windowbase-class), [top](top) will return a reference to
the [WindowBase](../windowbase-class) itself.

``` {.language-dart data-language="dart"}
// Add an IFrame to the current window.
IFrameElement myIFrame = new IFrameElement();
window.document.body.elements.add(myIFrame);

// Add an IFrame inside of the other IFrame.
IFrameElement innerIFrame = new IFrameElement();
myIFrame.elements.add(innerIFrame);

print(myIframe.contentWindow.top == window) // 'true'
print(innerIFrame.contentWindow.top == window) // 'true'

print(window.top == window) // 'true'
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
WindowBase? get top;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WindowBase/top.html>
:::
