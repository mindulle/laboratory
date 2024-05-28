[dart:html](../../dart-html/dart-html-library){._links-link}

getString method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[String](../../dart-core/string-class)\>
getString(

1.  [String](../../dart-core/string-class) url,
2.  {[bool](../../dart-core/bool-class)? withCredentials,
3.  void onProgress(
    1.  [ProgressEvent](../progressevent-class) e

    )?}

)
:::

Creates a GET request for the specified `url`.

This is similar to [request](request) but specialized for HTTP GET
requests which return text content.

To add query parameters, append them to the `url` following a `?`,
joining each key to its value with `=` and separating key-value pairs
with `&`.

``` {.language-dart data-language="dart"}
var name = Uri.encodeQueryComponent('John');
var id = Uri.encodeQueryComponent('42');
HttpRequest.getString('users.json?name=$name&id=$id')
  .then((String resp) {
    // Do something with the response.
});
```

See also:

-   [request](request)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<String> getString(String url,
    {bool? withCredentials, void onProgress(ProgressEvent e)?}) {
  return request(url,
          withCredentials: withCredentials, onProgress: onProgress)
      .then((HttpRequest xhr) => xhr.responseText!);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/getString.html>
:::
