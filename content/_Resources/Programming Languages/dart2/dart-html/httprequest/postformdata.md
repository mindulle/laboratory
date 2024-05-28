[dart:html](../../dart-html/dart-html-library){._links-link}

postFormData method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpRequest](../httprequest-class)\>
postFormData(

1.  [String](../../dart-core/string-class) url,
2.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)\> data,
3.  {[bool](../../dart-core/bool-class)? withCredentials,
4.  [String](../../dart-core/string-class)? responseType,
5.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)\>? requestHeaders,
6.  void onProgress(
    1.  [ProgressEvent](../progressevent-class) e

    )?}

)
:::

Makes a server POST request with the specified data encoded as form
data.

This is roughly the POST equivalent of [getString](getstring). This
method is similar to sending a [FormData](../formdata-class) object with
broader browser support but limited to String values.

If `data` is supplied, the key/value pairs are URI encoded with
[Uri.encodeQueryComponent](../../dart-core/uri/encodequerycomponent) and
converted into an HTTP query string.

Unless otherwise specified, this method appends the following header:

``` {.language-dart data-language="dart"}
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
```

Here\'s an example of using this method:

``` {.language-dart data-language="dart"}
var data = { 'firstName' : 'John', 'lastName' : 'Doe' };
HttpRequest.postFormData('/send', data).then((HttpRequest resp) {
  // Do something with the response.
});
```

See also:

-   [request](request)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<HttpRequest> postFormData(String url, Map<String, String> data,
    {bool? withCredentials,
    String? responseType,
    Map<String, String>? requestHeaders,
    void onProgress(ProgressEvent e)?}) {
  var parts = [];
  data.forEach((key, value) {
    parts.add('${Uri.encodeQueryComponent(key)}='
        '${Uri.encodeQueryComponent(value)}');
  });
  var formData = parts.join('&');

  if (requestHeaders == null) {
    requestHeaders = <String, String>{};
  }
  requestHeaders.putIfAbsent('Content-Type',
      () => 'application/x-www-form-urlencoded; charset=UTF-8');

  return request(url,
      method: 'POST',
      withCredentials: withCredentials,
      responseType: responseType,
      requestHeaders: requestHeaders,
      sendData: formData,
      onProgress: onProgress);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/postFormData.html>
:::
