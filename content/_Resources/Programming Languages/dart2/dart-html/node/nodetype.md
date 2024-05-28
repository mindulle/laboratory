[dart:html](../../dart-html/dart-html-library){._links-link}

nodeType property
=================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) nodeType
:::

The type of node.

This value is one of:

-   [ATTRIBUTE\_NODE](attribute_node-constant) if this node is an
    attribute.
-   [CDATA\_SECTION\_NODE](cdata_section_node-constant) if this node is
    a [CDataSection](../cdatasection-class){.deprecated}.
-   [COMMENT\_NODE](comment_node-constant) if this node is a
    [Comment](../comment-class).
-   [DOCUMENT\_FRAGMENT\_NODE](document_fragment_node-constant) if this
    node is a [DocumentFragment](../documentfragment-class).
-   [DOCUMENT\_NODE](document_node-constant) if this node is a
    [Document](../document-class).
-   [DOCUMENT\_TYPE\_NODE](document_type_node-constant) if this node is
    a `_DocumentType` node.
-   [ELEMENT\_NODE](element_node-constant) if this node is an
    [Element](../element-class).
-   [ENTITY\_NODE](entity_node-constant) if this node is an entity.
-   [ENTITY\_REFERENCE\_NODE](entity_reference_node-constant) if this
    node is an entity reference.
-   [NOTATION\_NODE](notation_node-constant) if this node is a notation.
-   [PROCESSING\_INSTRUCTION\_NODE](processing_instruction_node-constant)
    if this node is a
    [ProcessingInstruction](../processinginstruction-class).
-   [TEXT\_NODE](text_node-constant) if this node is a
    [Text](../text-class) node.

Other resources
---------------

-   [Node.nodeType](https://developer.mozilla.org/en-US/docs/Web/API/Node.nodeType)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get nodeType native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/nodeType.html>
:::
