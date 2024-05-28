[dart:html](../../dart-html/dart-html-library){._links-link}

resolveLocalFileSystemUrl method
================================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'webkitResolveLocalFileSystemURL\')
2.  \@SupportedBrowser(SupportedBrowser.CHROME)

</div>

[Future](../../dart-async/future-class)\<[Entry](../entry-class)\>
resolveLocalFileSystemUrl(

1.  [String](../../dart-core/string-class) url

)

::: {.features}
\@JSName(\'webkitResolveLocalFileSystemURL\'),
\@SupportedBrowser(SupportedBrowser.CHROME)
:::
:::

Asynchronously retrieves a local filesystem entry.

Other resources
---------------

-   [Obtaining access to file system entry
    points](http://www.w3.org/TR/file-system-api/#obtaining-access-to-file-system-entry-points)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('webkitResolveLocalFileSystemURL')
/**
 * Asynchronously retrieves a local filesystem entry.
 *
 * ## Other resources
 *
 * * [Obtaining access to file system entry
 *   points](http://www.w3.org/TR/file-system-api/#obtaining-access-to-file-system-entry-points)
 * from W3C.
 */
@SupportedBrowser(SupportedBrowser.CHROME)
Future<Entry> resolveLocalFileSystemUrl(String url) {
  var completer = new Completer<Entry>();
  _resolveLocalFileSystemUrl(url, (value) {
    completer.complete(value);
  }, (error) {
    completer.completeError(error);
  });
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/resolveLocalFileSystemUrl.html>
:::
