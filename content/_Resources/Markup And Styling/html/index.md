HTML: HyperText Markup Language
===============================

**HTML** (HyperText Markup Language) is the most basic building block of
the Web. It defines the meaning and structure of web content. Other
technologies besides HTML are generally used to describe a web page\'s
appearance/presentation
([CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)) or
functionality/behavior
([JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)).

\"Hypertext\" refers to links that connect web pages to one another,
either within a single website or between websites. Links are a
fundamental aspect of the Web. By uploading content to the Internet and
linking it to pages created by other people, you become an active
participant in the World Wide Web.

HTML uses \"markup\" to annotate text, images, and other content for
display in a Web browser. HTML markup includes special \"elements\" such
as [`<head>`](element/head), [`<title>`](element/title),
[`<body>`](element/body), [`<header>`](element/header),
[`<footer>`](element/footer), [`<article>`](element/article),
[`<section>`](element/section), [`<p>`](element/p),
[`<div>`](element/div), [`<span>`](element/span),
[`<img>`](element/img), [`<aside>`](element/aside),
[`<audio>`](element/audio), [`<canvas>`](element/canvas),
[`<datalist>`](element/datalist), [`<details>`](element/details),
[`<embed>`](element/embed), [`<nav>`](element/nav),
[`<search>`](element/search), [`<output>`](element/output),
[`<progress>`](element/progress), [`<video>`](element/video),
[`<ul>`](element/ul), [`<ol>`](element/ol), [`<li>`](element/li) and
many others.

An HTML element is set off from other text in a document by \"tags\",
which consist of the element name surrounded by \"`<`\" and \"`>`\". The
name of an element inside a tag is case-insensitive. That is, it can be
written in uppercase, lowercase, or a mixture. For example, the
`<title>` tag can be written as `<Title>`, `<TITLE>`, or in any other
way. However, the convention and recommended practice is to write tags
in lowercase.

The articles below can help you learn more about HTML.

Key resources
-------------

[HTML Introduction](#html_introduction)

:   If you\'re new to web development, be sure to read our [HTML
    Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
    article to learn what HTML is and how to use it.

[HTML Tutorials](#html_tutorials)

:   For articles about how to use HTML, as well as tutorials and
    complete examples, check out our [HTML Learning
    Area](https://developer.mozilla.org/en-US/docs/Learn/HTML).

[HTML Reference](#html_reference)

:   In our extensive [HTML reference](reference) section, you\'ll find
    the details about every element and attribute in HTML.

#### Looking to become a front-end web developer?

We have put together a course that includes all the essential
information you need to work towards your goal.

[**Get
started**](https://developer.mozilla.org/en-US/docs/Learn/Front-end_web_developer)

Beginner\'s tutorials
---------------------

Our [HTML Learning
Area](https://developer.mozilla.org/en-US/docs/Learn/HTML) features
multiple modules that teach HTML from the ground up --- no previous
knowledge required.

[Introduction to HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)

:   This module sets the stage, getting you used to important concepts
    and syntax such as looking at applying HTML to text, how to create
    hyperlinks, and how to use HTML to structure a web page.

[Multimedia and embedding](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding)

:   This module explores how to use HTML to include multimedia in your
    web pages, including the different ways that images can be included,
    and how to embed video, audio, and even entire other webpages.

[HTML tables](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables)

:   Representing tabular data on a webpage in an understandable,
    accessible way can be a challenge. This module covers basic table
    markup, along with more complex features such as implementing
    captions and summaries.

[HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)

:   Forms are a very important part of the Web --- these provide much of
    the functionality you need for interacting with websites, e.g.
    registering and logging in, sending feedback, buying products, and
    more. This module gets you started with creating the
    client-side/front-end parts of forms.

[Use HTML to solve common problems](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto)

:   Provides links to sections of content explaining how to use HTML to
    solve very common problems when creating a web page: dealing with
    titles, adding images or videos, emphasizing content, creating a
    basic form, etc.

Advanced topics
---------------

[CORS enabled image](cors_enabled_image)

:   The [`crossorigin`](element/img#crossorigin) attribute, in
    combination with an appropriate
    [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
    header, allows images defined by the [`<img>`](element/img) element
    to be loaded from foreign origins and used in a
    [`<canvas>`](element/canvas) element as if they were being loaded
    from the current origin.

[CORS settings attributes](attributes/crossorigin)

:   Some HTML elements that provide support for
    [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS), such
    as [`<img>`](element/img) or [`<video>`](element/video), have a
    `crossorigin` attribute (`crossOrigin` property), which lets you
    configure the CORS requests for the element\'s fetched data.

[Preloading content with rel=\"preload\"](attributes/rel/preload)

:   The `preload` value of the [`<link>`](element/link) element\'s
    [`rel`](element/link#rel) attribute allows you to write declarative
    fetch requests in your HTML [`<head>`](element/head), specifying
    resources that your pages will need very soon after loading, which
    you therefore want to start preloading early in the lifecycle of a
    page load, before the browser\'s main rendering machinery kicks in.
    This ensures that they are made available earlier and are less
    likely to block the page\'s first render, leading to performance
    improvements. This article provides a basic guide to how `preload`
    works.

Reference
---------

[HTML reference](reference)

:   HTML consists of **elements**, each of which may be modified by some
    number of **attributes**. HTML documents are connected to each other
    with **links**.

[HTML element reference](_Resources/Markup%20And%20Styling/html/element/index.md)

:   Browse a list of all
    [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML)
    [elements](https://developer.mozilla.org/en-US/docs/Glossary/Element).

[HTML attribute reference](_Resources/Markup%20And%20Styling/html/attributes/index.md)

:   Elements in HTML have **attributes**. These are additional values
    that configure the elements or adjust their behavior in various
    ways.

[Global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md)

:   Global attributes may be specified on all [HTML elements](_Resources/Markup%20And%20Styling/html/element/index.md),
    *even those not specified in the standard*. This means that any
    non-standard elements must still permit these attributes, even
    though those elements make the document HTML5-noncompliant.

[Inline-level elements](https://developer.mozilla.org/en-US/docs/Glossary/Inline-level_content) and [block-level elements](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content)

:   HTML elements are usually \"inline-level\" or \"block-level\"
    elements. An inline-level element occupies only the space bounded by
    the tags that define it. A block-level element occupies the entire
    space of its parent element (container), thereby creating a \"block
    box\".

[Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)

:   The [`<audio>`](element/audio) and [`<video>`](element/video)
    elements allow you to play audio and video media natively within
    your content without the need for external software support.

[HTML content categories](content_categories)

:   HTML is comprised of several kinds of content, each of which is
    allowed to be used in certain contexts and is disallowed in others.
    Similarly, each context has a set of other content categories it can
    contain and elements that can or can\'t be used in them. This is a
    guide to these categories.

[Quirks mode and standards mode](quirks_mode_and_standards_mode)

:   Historical information on quirks mode and standards mode.

Related topics
--------------

[Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors/Applying_color)

:   This article covers most of the ways you use CSS to add color to
    HTML content, listing what parts of HTML documents can be colored
    and what CSS properties to use when doing so. Includes examples,
    links to palette-building tools, and more.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML>>
