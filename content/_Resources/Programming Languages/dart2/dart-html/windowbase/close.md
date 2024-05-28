[dart:html](../../dart-html/dart-html-library){._links-link}

close method
============

::: {.section .multi-line-signature}
void close()
:::

Closes the window.

This method should only succeed if the [WindowBase](../windowbase-class)
object is **script-closeable** and the window calling [close](close) is
allowed to navigate the window.

A window is script-closeable if it is either a window that was opened by
another window, or if it is a window with only one document in its
history.

A window might not be allowed to navigate, and therefore close, another
window due to browser security features.

``` {.language-dart data-language="dart"}
var other = window.open('http://www.example.com', 'foo');
// Closes other window, as it is script-closeable.
other.close();
print(other.closed); // 'true'

var newLocation = window.location
    ..href = 'http://www.mysite.com';
window.location = newLocation;
// Does not close this window, as the history has changed.
window.close();
print(window.closed); // 'false'
```

See also:

-   [Window close
    discussion](http://www.w3.org/TR/html5/browsers.html#dom-window-close)
    from the W3C

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WindowBase/close.html>
:::
