\<script type=\"speculationrules\"\>
====================================

The `speculationrules` value of the [`type`](../type) attribute of the
[`<script>` element](../../script) indicates that the body of the
element contains speculation rules.

Speculation rules take the form of a JSON structure that determine what
resources should be prefetched or prerendered by the browser. This is
part of the [Speculation Rules
API](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API).

Syntax
------

[html]

```html
<script type="speculationrules">
  // JSON object defining rules
</script>
```

**Note:** The `src`, `async`, `nomodule`, `defer`, `crossorigin`,
`integrity`, and `referrerpolicy` attributes must not be specified.

### Exceptions

[`TypeError`](#typeerror)

:   The speculation rules definition is not a valid JSON object.

Description
-----------

A `<script type="speculationrules">` element must contain a valid JSON
structure that defines speculation rules. The following examples show
separate prefetch and prerender rules:

[html]

```html
<script type="speculationrules">
  {
    "prefetch": [
      {
        "source": "list",
        "urls": ["next.html", "next2.html"],
        "requires": ["anonymous-client-ip-when-cross-origin"],
        "referrer_policy": "no-referrer"
      }
    ]
  }
</script>
```

[html]

```html
<script type="speculationrules">
  {
    "prerender": [
      {
        "source": "list",
        "urls": ["next3.html", "next4.html"]
      }
    ]
  }
</script>
```

### Speculation rules JSON representation

The JSON structure contains one or more fields at the top level, each
one representing an action to define speculation rules for. At present
the supported actions are:

[`"prefetch"`](#prefetch) [Optional]

:   Rules for potential future navigations that should have their
    associated document response body downloaded, leading to significant
    performance improvements when those documents are navigated to. Note
    that none of the subresources referenced by the page are downloaded.

[`"prerender"`](#prerender) [Optional]

:   Rules for potential future navigations that should have their
    associated documents fully downloaded, rendered, and loaded into an
    invisible tab. This includes loading all subresources, running all
    JavaScript, and even loading subresources and performing data
    fetches started by JavaScript. When those documents are navigated
    to, navigations will be instant, leading to major performance
    improvements.

**Note:** Consult the [Speculation Rules
API](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API)
main page for full details on how to use prefetch and prerender
effectively.

Each action field contains an array, which in turn contains one or more
objects. Each object contains a single rule defining a set of URLs and
related parameters.

Specifically, each object can contain the following properties:

[`"source"`](#source)

:   A string representing the source of the URLs to which the rule
    applies. Possible values are:

    [`"list"`](#list)

    :   Denotes that the URLs will come from a specific list.

[`"urls"`](#urls)

:   An array of strings representing the list of URLs to apply the rule
    to. These can be absolute or relative URLs. Relative URLs will be
    parsed relative to the document base URL (if inline in a document)
    or relative to the external resource URL (if externally fetched).

[`"requires"`](#requires) [Optional]

:   An array of strings representing capabilities of the browser parsing
    the rule, which must be available if the rule is to be applied to
    the specified URLs.

    **Warning:** Prefetches will automatically fail in browsers that
    cannot meet a specified requirement, even if they support the
    [Speculation Rules
    API](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API).
    

    Possible values are:

    [`"anonymous-client-ip-when-cross-origin"`](#anonymous-client-ip-when-cross-origin)

    :   `"prefetch"`-only. Specifies that the rule matches only if the
        user agent can prevent the client IP address from being visible
        to the origin server if a cross-origin prefetch request is
        issued. Exactly how this works is dependent on browser
        implementation specifics. For example:

        -   Chrome\'s implementation hides the IP address using a
            Google-owned proxy, therefore by default it only works for
            Google-controlled referrers (since in that case, sending the
            URLs of the destination to Google is not an additional
            privacy leak). When used on a non-Google-owned site, rules
            that include this will only match for users that turn on
            \"Enhanced preloading\" in `chrome://settings/preloading`.
        -   Other Chromium-based browsers will have to provide their own
            solutions. Thorough testing in all target browsers is
            advised.
        -   A future Safari implementation may possibly use something
            along the lines of [iCloud Private
            Relay](https://support.apple.com/en-us/102602).
        -   A future Firefox implementation might use something based on
            the [Mozilla
            VPN](https://www.mozilla.org/en-US/products/vpn/) product.

[`"referrer_policy"`](#referrer_policy) [Optional]

:   A string representing a specific referrer policy string to use when
    requesting the URLs specified in the rule --- see
    [`Referrer-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy)
    for possible values. The purpose of this is to allow the referring
    page to set a stricter policy specifically for the speculative
    request than the policy the page already has set (either by default,
    or by using `Referrer-Policy`). A laxer policy set in the
    speculation rules will not override a stricter policy set on the
    referring page.

**Note:** As speculation rules use a `<script>` element, they need to be
explicitly allowed in the
[`Content-Security-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy)
[`script-src`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/script-src)
directive if the site includes it. This is done by adding the
`"inline-speculation-rules"` value along with a hash- or nonce-source.

### Further examples

The earlier examples showed separate speculation rules defined for
prefetch and prerender. It is possible to define both in a single set of
rules:

[html]

```html
<script type="speculationrules">
  {
    "prefetch": [
      {
        "source": "list",
        "urls": ["next.html", "next2.html"],
        "requires": ["anonymous-client-ip-when-cross-origin"],
        "referrer_policy": "no-referrer"
      }
    ],
    "prerender": [
      {
        "source": "list",
        "urls": ["next3.html", "next4.html"]
      }
    ]
  }
</script>
```

It is also allowable to include multiple sets of rules in a single HTML
file:

[html]

```html
<script type="speculationrules">
  {
    "prefetch": [
      {
        "source": "list",
        "urls": ["next.html", "next2.html"],
        "requires": ["anonymous-client-ip-when-cross-origin"],
        "referrer_policy": "no-referrer"
      }
    ]
  }
</script>
<script type="speculationrules">
  {
    "prerender": [
      {
        "source": "list",
        "urls": ["next3.html", "next4.html"]
      }
    ]
  }
</script>
```

And multiple rules in a single result set:

[js]

```js
<script type="speculationrules">
{
  "prerender": [
    {
      "source": "list",
      "urls": ["one.html"]
    },
    {
      "source": "list",
      "urls": ["two.html"]
    }
  ]
}
</script>
```

### Dynamic rule insertion

Below is an example that feature detects speculation rules and, if
supported, dynamically adds a prerender speculation rule via JavaScript:

[js]

```js
if (
  HTMLScriptElement.supports &&
  HTMLScriptElement.supports("speculationrules")
) {
  const specScript = document.createElement("script");
  specScript.type = "speculationrules";
  const specRules = {
    prerender: [
      {
        source: "list",
        urls: ["/next.html"],
      },
    ],
  };
  specScript.textContent = JSON.stringify(specRules);
  console.log("added speculation rules to: next.html");
  document.body.append(specScript);
}
```

You can see this in action in this [prerender
demos](https://prerender-demos.glitch.me/) page.

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------------------

  [Speculation Rules\
  [\#
  speculation-rules-script]](https://wicg.github.io/nav-speculation/speculation-rules.html#speculation-rules-script)

  ----------------------------------------------------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`speculationrules`

109

105Initial support included same-origin prerendering only.

109

105Initial support included same-origin prerendering only.

No

No

95

91Initial support included same-origin prerendering only.

No

109

103Initial support included same-origin prerendering only.

109

103Initial support included same-origin prerendering only.

No

74

71Initial support included same-origin prerendering only.

No

21.0

20.0Initial support included same-origin prerendering only.

`prefetch`

110

110

No

No

96

No

103

103

No

71

No

20.0

`referrer_policy`

111

111

No

No

97

No

111

111

No

No

No

22.0

`requires`

110

110

No

No

96

No

103

103

No

71

No

20.0

See also
--------

- [Prerender pages in Chrome for instant page
    navigations](https://developer.chrome.com/blog/prerender-pages/) on
    developer.chrome.com (2023)
- [Speculative
    loading](https://developer.mozilla.org/en-US/docs/Web/Performance/Speculative_loading)
- [Speculation Rules
    API](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script/type/speculationrules>>
