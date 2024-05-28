[dart:html](../../dart-html/dart-html-library){._links-link}

request method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpRequest](../httprequest-class)\>
request(

1.  [String](../../dart-core/string-class) url,
2.  {[String](../../dart-core/string-class)? method,
3.  [bool](../../dart-core/bool-class)? withCredentials,
4.  [String](../../dart-core/string-class)? responseType,
5.  [String](../../dart-core/string-class)? mimeType,
6.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)\>? requestHeaders,
7.  dynamic sendData,
8.  void onProgress(
    1.  [ProgressEvent](../progressevent-class) e

    )?}

)
:::

Creates and sends a URL request for the specified `url`.

By default `request` will perform an HTTP GET request, but a different
method (`POST`, `PUT`, `DELETE`, etc) can be used by specifying the
`method` parameter. (See also [HttpRequest.postFormData](postformdata)
for `POST` requests only.

The Future is completed when the response is available.

If specified, `sendData` will send data in the form of a
[ByteBuffer](../../dart-typed_data/bytebuffer-class),
[Blob](../blob-class), [Document](../document-class),
[String](../../dart-core/string-class), or [FormData](../formdata-class)
along with the HttpRequest.

If specified, `responseType` sets the desired response format for the
request. By default it is [String](../../dart-core/string-class), but
can also be \'arraybuffer\', \'blob\', \'document\', \'json\', or
\'text\'. See also [HttpRequest.responseType](responsetype) for more
information.

The `withCredentials` parameter specified that credentials such as a
cookie (already) set in the header or [authorization
headers](http://tools.ietf.org/html/rfc1945#section-10.2) should be
specified for the request. Details to keep in mind when using
credentials:

-   Using credentials is only useful for cross-origin requests.
-   The `Access-Control-Allow-Origin` header of `url` cannot contain a
    wildcard (\*).
-   The `Access-Control-Allow-Credentials` header of `url` must be set
    to true.
-   If `Access-Control-Expose-Headers` has not been set to true, only a
    subset of all the response headers will be returned when calling
    [getAllResponseHeaders](getallresponseheaders).

The following is equivalent to the [getString](getstring) sample above:

``` {.language-dart data-language="dart"}
var name = Uri.encodeQueryComponent('John');
var id = Uri.encodeQueryComponent('42');
HttpRequest.request('users.json?name=$name&id=$id')
  .then((HttpRequest resp) {
    // Do something with the response.
});
```

Here\'s an example of submitting an entire form with
[FormData](../formdata-class).

``` {.language-dart data-language="dart"}
var myForm = querySelector('form#myForm');
var data = new FormData(myForm);
HttpRequest.request('/submit', method: 'POST', sendData: data)
  .then((HttpRequest resp) {
    // Do something with the response.
});
```

Note that requests for file:// URIs are only supported by Chrome
extensions with appropriate permissions in their manifest. Requests to
file:// URIs will also never fail- the Future will always complete
successfully, even when the file cannot be found.

See also: [authorization
headers](http://en.wikipedia.org/wiki/Basic_access_authentication).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<HttpRequest> request(String url,
    {String? method,
    bool? withCredentials,
    String? responseType,
    String? mimeType,
    Map<String, String>? requestHeaders,
    sendData,
    void onProgress(ProgressEvent e)?}) {
  var completer = new Completer<HttpRequest>();

  var xhr = new HttpRequest();
  if (method == null) {
    method = 'GET';
  }
  xhr.open(method, url, async: true);

  if (withCredentials != null) {
    xhr.withCredentials = withCredentials;
  }

  if (responseType != null) {
    xhr.responseType = responseType;
  }

  if (mimeType != null) {
    xhr.overrideMimeType(mimeType);
  }

  if (requestHeaders != null) {
    requestHeaders.forEach((header, value) {
      xhr.setRequestHeader(header, value);
    });
  }

  if (onProgress != null) {
    xhr.onProgress.listen(onProgress);
  }

  xhr.onLoad.listen((e) {
    var status = xhr.status!;
    var accepted = status >= 200 && status < 300;
    var fileUri = status == 0; // file:// URIs have status of 0.
    var notModified = status == 304;
    // Redirect status is specified up to 307, but others have been used in
    // practice. Notably Google Drive uses 308 Resume Incomplete for
    // resumable uploads, and it's also been used as a redirect. The
    // redirect case will be handled by the browser before it gets to us,
    // so if we see it we should pass it through to the user.
    var unknownRedirect = status > 307 && status < 400;

    if (accepted || fileUri || notModified || unknownRedirect) {
      completer.complete(xhr);
    } else {
      completer.completeError(e);
    }
  });

  xhr.onError.listen(completer.completeError);

  if (sendData != null) {
    xhr.send(sendData);
  } else {
    xhr.send();
  }

  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/request.html>
:::
