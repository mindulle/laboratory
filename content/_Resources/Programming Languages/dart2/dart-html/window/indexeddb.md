[dart:html](../../dart-html/dart-html-library){._links-link}

indexedDB property
==================

::: {#getter .section .multi-line-signature}
[IdbFactory](../../dart-indexed_db/idbfactory-class)? indexedDB

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'23.0\'),
\@SupportedBrowser(SupportedBrowser.FIREFOX, \'15.0\'),
\@SupportedBrowser(SupportedBrowser.IE, \'10.0\')
:::
:::

Gets an instance of the Indexed DB factory to being using Indexed DB.

Use
[dart:indexed\_db.IdbFactory.supported](../../dart-indexed_db/idbfactory/supported)
to check if Indexed DB is supported on the current platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME, '23.0')
@SupportedBrowser(SupportedBrowser.FIREFOX, '15.0')
@SupportedBrowser(SupportedBrowser.IE, '10.0')
IdbFactory? get indexedDB => JS(
    'IdbFactory|Null', // If not supported, returns null.
    '#.indexedDB || #.webkitIndexedDB || #.mozIndexedDB',
    this,
    this,
    this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/indexedDB.html>
:::
