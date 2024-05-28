[dart:html](../../dart-html/dart-html-library){._links-link}

StorageEvent constructor
========================

::: {.section .multi-line-signature}
StorageEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[bool](../../dart-core/bool-class) canBubble = false,
3.  [bool](../../dart-core/bool-class) cancelable = false,
4.  [String](../../dart-core/string-class)? key,
5.  [String](../../dart-core/string-class)? oldValue,
6.  [String](../../dart-core/string-class)? newValue,
7.  [String](../../dart-core/string-class)? url,
8.  [Storage](../storage-class)? storageArea}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StorageEvent(String type,
    {bool canBubble: false,
    bool cancelable: false,
    String? key,
    String? oldValue,
    String? newValue,
    String? url,
    Storage? storageArea}) {
  StorageEvent e = document._createEvent("StorageEvent") as StorageEvent;
  e._initStorageEvent(
      type, canBubble, cancelable, key, oldValue, newValue, url, storageArea);
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/StorageEvent/StorageEvent.html>
:::
