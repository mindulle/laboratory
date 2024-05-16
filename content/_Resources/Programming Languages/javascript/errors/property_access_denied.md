Error: Permission denied to access property \"x\"
=================================================

 
The JavaScript exception \"Permission denied to access property\" occurs
when there was an attempt to access an object for which you have no
permission.


 
Message
-------

 
```text
DOMException: Blocked a frame with origin "x" from accessing a cross-origin frame. (Chromium-based)
DOMException: Permission denied to access property "x" on cross-origin object (Firefox)
SecurityError: Blocked a frame with origin "x" from accessing a cross-origin frame. Protocols, domains, and ports must match. (Safari)
```



 
Error type 
----------

 
[`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException).



 
What went wrong? 
----------------

 
There was attempt to access an object for which you have no permission.
This is likely an
[`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)
element loaded from a different domain for which you violated the
[same-origin
policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy).



 
Examples
--------


 
### No permission to access document 

 
 
 
[html]


```html
<!doctype html>
<html lang="en-US">
  <head>
    <iframe
      id="myframe"
      src="http://www1.w3c-test.org/common/blank.html"></iframe>
    <script>
      onload = function () {
        console.log(frames[0].document);
        // Error: Permission denied to access property "document"
      };
    </script>
  </head>
  <body></body>
</html>
```




 
See also 
--------

 
-   [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)
-   [Same-origin
    policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Property_access_denied>

