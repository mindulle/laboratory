container-name
==============

The **container-name**
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies a list of query container names used by the
[\@container](@container.md) at-rule in a [](css_container_queries.md). A container query will apply styles to
elements based on the size of the nearest ancestor with a containment
context. When a containment context is given a name, it can be
specifically targeted using the [`@container`](@container.md) at-rule
instead of the nearest ancestor with containment.

Syntax
------

[css]

```css
/* A single name */
container-name: myLayout;

/* Multiple names */
container-name: myPageLayout myComponentLibrary;

/* Global Values */
container-name: inherit;
container-name: initial;
container-name: revert;
container-name: revert-layer;
container-name: unset;
```

### Values

[`<container-name>`](#container-name)

:   A case-sensitive string that is used to identify the container.

    The following conditions apply:

    -   The name can be any valid [`<custom-ident>`](custom-ident), but
        must not equal `default`.
    -   The name value must not be in quotes.
    -   The dashed ident intended to denote author-defined identifiers
        (e.g., `--container-name`) is permitted.
    -   A list of multiple names separated by a space is allowed.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   `none` or an ordered list of identifiers
  Animation type                     Not animatable
  ---------------------------------- ------------------------------------------

Formal syntax
-------------

```
container-name = 
  none             |
  <custom-ident>+  
```

Examples
--------

### Using a container name

Given the following HTML example which is a card component with a title
and some text:

[html]

```html
<div class="card">
  <div class="post-meta">
    <h2>Card title</h2>
    <p>My post details.</p>
  </div>
  <div class="post-excerpt">
    <p>
      A preview of my <a href="https://example.com">blog post</a> about cats.
    </p>
  </div>
</div>
```

To create a containment context, add the `container-type` property to an
element in CSS. The following example creates two containment contexts,
one for the card meta information and one for the post excerpt:

**Note:** A shorthand syntax for these declarations are described in the
[`container`](container.md) page.

[css]

```css
.post-meta {
  container-type: inline-size;
}

.post-excerpt {
  container-type: inline-size;
  container-name: excerpt;
}
```

Writing a container query via the [`@container`](@container.md) at-rule
will apply styles to the elements of the container when the query
evaluates to true. The following example has two container queries, one
that will apply only to the contents of the `.post-excerpt` element and
one that will apply to both the `.post-meta` and `.post-excerpt`
contents:

[css]

```css
@container excerpt (min-width: 400px) {
  p {
    visibility: hidden;
  }
}

@container (min-width: 400px) {
  p {
    font-size: 2rem;
  }
}
```

For more information on writing container queries, see the [](css_container_queries.md) page.

### Using multiple container names

You can also provide multiple names to a container context separated by
a space:

[css]

```css
.post-meta {
  container-type: inline-size;
  container-name: meta card;
}
```

This will allow you to target the container using either name in the
[`@container`](@container.md) at-rule. This is useful if you want to target
the same container with multiple container queries where either
condition could be true:

[css]

```css
@container meta (max-width: 500px) {
  p {
    visibility: hidden;
  }
}

@container card (max-height: 200px) {
  h2 {
    font-size: 1.5em;
  }
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Containment Module Level 3\
  [\#
  container-name]](https://drafts.csswg.org/css-contain-3/#container-name)

  ----------------------------------------------------------------------------------

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

`container-name`

105

105

110

No

91

16

105

105

110

72

16

20.0

See also
--------

- [CSS container queries](css_container_queries.md)
- [`@container`](@container.md) at-rule
- CSS [`container`](container.md) shorthand property
- CSS [`container-type`](container-type.md) property
- CSS [`content-visibility`](content-visibility.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/container-name>
