[dart:html](../dart-html/dart-html-library){._links-link}

HttpRequest class
=================

A client-side XHR request for getting data from a URL, formally known as
XMLHttpRequest.

HttpRequest can be used to obtain data from HTTP and FTP protocols, and
is useful for AJAX-style page updates.

The simplest way to get the contents of a text file, such as a
JSON-formatted file, is with [getString](httprequest/getstring). For
example, the following code gets the contents of a JSON file and prints
its length:

``` {.language-dart data-language="dart"}
var path = 'myData.json';
HttpRequest.getString(path).then((String fileContents) {
  print(fileContents.length);
}).catchError((error) {
  print(error.toString());
});
```

Fetching data from other servers
--------------------------------

For security reasons, browsers impose restrictions on requests made by
embedded apps. With the default behavior of this class, the code making
the request must be served from the same origin (domain name, port, and
application layer protocol) as the requested resource. In the example
above, the myData.json file must be co-located with the app that uses
it.

Other resources
---------------

-   [Fetch data
    dynamically](https://dart.dev/tutorials/web/fetch-data/), a tutorial
    shows how to load data from a static file or from a server.
-   [Dart article on using
    HttpRequests](https://dart.dev/guides/libraries/library-tour#using-http-resources-with-httprequest)
-   [JS
    XMLHttpRequest](https://developer.mozilla.org/en-US/docs/DOM/XMLHttpRequest)
-   [Using
    XMLHttpRequest](https://developer.mozilla.org/en-US/docs/DOM/XMLHttpRequest/Using_XMLHttpRequest)

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [HttpRequestEventTarget](httprequesteventtarget-class)
    -   HttpRequest

Annotations

:   -   \@Native(\"XMLHttpRequest\")

Constructors
------------

[HttpRequest](httprequest/httprequest)()

::: {.constructor-modifier .features}
factory
:::

General constructor for any type of request (GET, POST, etc).

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAbort](httprequesteventtarget/onabort) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `abort` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onError](httprequesteventtarget/onerror) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `error` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onLoad](httprequesteventtarget/onload) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `load` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onLoadEnd](httprequesteventtarget/onloadend) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only, inherited
:::

Stream of `loadend` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onLoadStart](httprequesteventtarget/onloadstart) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `loadstart` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onProgress](httprequesteventtarget/onprogress) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only, inherited
:::

Stream of `progress` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onReadyStateChange](httprequest/onreadystatechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Event listeners to be notified every time the
[HttpRequest](httprequest-class) object\'s `readyState` changes values.

[onTimeout](httprequesteventtarget/ontimeout) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `timeout` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[readyState](httprequest/readystate) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Indicator of the current state of the request:

[response](httprequest/response) → dynamic

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only
:::

The data received as a reponse from the request.

[responseHeaders](httprequest/responseheaders) →
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>

::: {.features}
read-only
:::

Returns all response headers as a key-value map.

[responseText](httprequest/responsetext) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

The response in String form or empty String on failure.

[responseType](httprequest/responsetype) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

[String](../dart-core/string-class) telling the server the desired
response format.

[responseUrl](httprequest/responseurl) →
[String](../dart-core/string-class)?

::: {.features}
\@JSName(\'responseURL\'), read-only
:::

[responseXml](httprequest/responsexml) → [Document](document-class)?

::: {.features}
\@JSName(\'responseXML\'), read-only
:::

The request response, or null on failure.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[status](httprequest/status) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

The HTTP result code from the request (200, 404, etc). See also: [HTTP
Status Codes](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

[statusText](httprequest/statustext) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

The request response string (such as \"OK\"). See also: [HTTP Status
Codes](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

[timeout](httprequest/timeout) ↔ [int](../dart-core/int-class)?

::: {.features}
read / write
:::

Length of time in milliseconds before a request is automatically
terminated.

[upload](httprequest/upload) →
[HttpRequestUpload](httprequestupload-class)

::: {.features}
\@Unstable(), read-only
:::

[EventTarget](eventtarget-class) that can hold listeners to track the
progress of the request.

[withCredentials](httprequest/withcredentials) ↔
[bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

True if cross-site requests should use credentials such as cookies or
authorization headers; false otherwise.

Methods {#instance-methods}
-------

[abort](httprequest/abort)() → void

Stop the current request.

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getAllResponseHeaders](httprequest/getallresponseheaders)() →
[String](../dart-core/string-class)

::: {.features}
\@Unstable()
:::

Retrieve all the response headers from a request.

[getResponseHeader](httprequest/getresponseheader)([String](../dart-core/string-class)
name) → [String](../dart-core/string-class)?

::: {.features}
\@Unstable()
:::

Return the response header named `header`, or null if not found.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[open](httprequest/open)([String](../dart-core/string-class) method,
[String](../dart-core/string-class) url,
{[bool](../dart-core/bool-class)? async,
[String](../dart-core/string-class)? user,
[String](../dart-core/string-class)? password}) → void

Specify the desired `url`, and `method` to use in making the request.

[overrideMimeType](httprequest/overridemimetype)([String](../dart-core/string-class)
mime) → void

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

Specify a particular MIME type (such as `text/xml`) desired for the
response.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[send](httprequest/send)(\[dynamic body\_OR\_data\]) → void

Send the request with any given `data`.

[setRequestHeader](httprequest/setrequestheader)([String](../dart-core/string-class)
name, [String](../dart-core/string-class) value) → void

Sets the value of an HTTP request header.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Properties
-----------------

[supportsCrossOrigin](httprequest/supportscrossorigin) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks to see if the current platform supports making cross origin
requests.

[supportsLoadEndEvent](httprequest/supportsloadendevent) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks to see if the LoadEnd event is supported on the current platform.

[supportsOverrideMimeType](httprequest/supportsoverridemimetype) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks to see if the overrideMimeType method is supported on the current
platform.

[supportsProgressEvent](httprequest/supportsprogressevent) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks to see if the Progress event is supported on the current
platform.

Static Methods
--------------

[getString](httprequest/getstring)([String](../dart-core/string-class) url, {[bool](../dart-core/bool-class)? withCredentials, void onProgress([ProgressEvent](progressevent-class) e)?}) → [Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>
:   Creates a GET request for the specified `url`.

[postFormData](httprequest/postformdata)([String](../dart-core/string-class) url, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\> data, {[bool](../dart-core/bool-class)? withCredentials, [String](../dart-core/string-class)? responseType, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\>? requestHeaders, void onProgress([ProgressEvent](progressevent-class) e)?}) → [Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>
:   Makes a server POST request with the specified data encoded as form
    data.

[request](httprequest/request)([String](../dart-core/string-class) url, {[String](../dart-core/string-class)? method, [bool](../dart-core/bool-class)? withCredentials, [String](../dart-core/string-class)? responseType, [String](../dart-core/string-class)? mimeType, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\>? requestHeaders, dynamic sendData, void onProgress([ProgressEvent](progressevent-class) e)?}) → [Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>
:   Creates and sends a URL request for the specified `url`.

[requestCrossOrigin](httprequest/requestcrossorigin)([String](../dart-core/string-class) url, {[String](../dart-core/string-class)? method, [String](../dart-core/string-class)? sendData}) → [Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>
:   Makes a cross-origin request to the specified URL.

Constants
---------

[DONE](httprequest/done-constant) → const [int](../dart-core/int-class)

:   <div>

    `4`

    </div>

[HEADERS\_RECEIVED](httprequest/headers_received-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[LOADING](httprequest/loading-constant) → const [int](../dart-core/int-class)

:   <div>

    `3`

    </div>

[OPENED](httprequest/opened-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

[readyStateChangeEvent](httprequest/readystatechangeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `readystatechange` events to event
    handlers that are not necessarily instances of
    [HttpRequest](httprequest-class).
    <div>

    `const EventStreamProvider<Event>('readystatechange')`

    </div>

[UNSENT](httprequest/unsent-constant) → const [int](../dart-core/int-class)

:   <div>

    `0`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest-class.html>
:::
