\@document
==========

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.

The `@document` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) restricts the style rules contained within it based
on the URL of the document. It is designed primarily for user-defined
style sheets, though it can be used on author-defined style sheets, too.

[css]

```css
@document url("https://www.example.com/")
{
  h1 {
    color: green;
  }
}
```

Syntax
------

An `@document` rule can specify one or more matching functions. If any
of the functions apply to a given URL, the rule will take effect on that
URL. The functions available are:

[`url()`](#url)

:   Matches an exact URL.

[`url-prefix()`](#url-prefix)

:   Matches if the document URL starts with the value provided.

[`domain()`](#domain)

:   Matches if the document URL is on the domain provided (or a
    subdomain of it).

[`media-document()`](#media-document)

:   Matches the media according to the string in parameter, one of
    `video`, `image`, `plugin` or `all`.

[`regexp()`](#regexp) [Deprecated]

:   Matches if the document URL is matched by the [regular
    expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
    provided. The expression must match the entire URL.

The values provided to the `url()`, `url-prefix()`, `domain()`, and
`media-document()` functions can be optionally enclosed by single or
double quotes. The values provided to the `regexp()` function *must* be
enclosed in quotes.

Escaped values provided to the `regexp()` function must additionally be
escaped from the CSS. For example, a `.` (period) matches any character
in regular expressions. To match a literal period, you would first need
to escape it using regular expression rules (to `\.`), then escape that
string using CSS rules (to `\\.`).

`@document` is currently only supported in Firefox; if you wanted to
replicate using such functionality in your own non-Firefox browser, you
could try using [this
polyfill](https://github.com/An-Error94/Handy-Scripts/tree/master/@document-polyfill)
by \@An-Error94, which uses a combination of a user script, [data-\*
attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*),
and [attribute selectors](attribute_selectors.md).

**Note:** There is a -moz-prefixed version of this property ---
`@-moz-document`. This has been limited to use only in user and UA
sheets in Firefox 59 in Nightly and Beta --- an experiment designed to
mitigate potential CSS injection attacks (See [Firefox bug
1035091](https://bugzil.la/1035091)).

Formal syntax
-------------

```
@document [ <url>                    |
            url-prefix(<string>)     |
            domain(<string>)         |
            media-document(<string>) |
            regexp(<string>)
          ]# {
  <group-rule-body>
}
```

Examples
--------

### Specifying document for CSS rule

[css]

```css
@document url("http://www.w3.org/"),
          url-prefix("http://www.w3.org/Style/"),
          domain("mozilla.org"),
          media-document("video"),
          regexp("https:.*") {
  /* CSS rules here apply to:
     - The page "http://www.w3.org/"
     - Any page whose URL begins with "http://www.w3.org/Style/"
     - Any page whose URL's host is "mozilla.org"
       or ends with ".mozilla.org"
     - Any standalone video
     - Any page whose URL starts with "https:" */

  /* Make the above-mentioned pages really ugly */
  body {
    color: purple;
    background: yellow;
  }
}
```

Specifications
--------------

[Initially](https://www.w3.org/TR/2012/WD-css3-conditional-20120911/#at-document)
in Level 3, `@document` was
[postponed](https://www.w3.org/TR/2012/WD-css3-conditional-20121213/#changes)
to Level 4, but then subsequently removed.

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

`@document`

No

No

61Only supports an empty `url-prefix()` value, which is supported due to
its [use in Firefox browser
detection](https://css-tricks.com/snippets/css/css-hacks-targeting-firefox/).
Still supported in user stylesheets.

1.5--61

No

No

No

No

No

61Only supports an empty `url-prefix()` value, which is supported due to
its [use in Firefox browser
detection](https://css-tricks.com/snippets/css/css-hacks-targeting-firefox/).
Still supported in user stylesheets.

4--61

No

No

No

`regexp`

No

No

6--61

No

No

No

No

No

6--61

No

No

No

See also
--------

- [Per-site user style sheet
    rules](https://lists.w3.org/Archives/Public/www-style/2004Aug/0135)
    on the www-style mailing list.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@document>
