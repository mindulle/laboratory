Package parse
=============

-   `import "text/template/parse"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package parse builds parse trees for templates as defined by
text/template and html/template. Clients should use those packages to
construct templates rather than this one, which provides shared internal
data structures not intended for general use.

Index 
-----

-   [func IsEmptyTree(n Node) bool](#IsEmptyTree)
-   [func Parse(name, text, leftDelim, rightDelim string, funcs
    \...map\[string\]any) (map\[string\]\*Tree, error)](#Parse)
-   [type ActionNode](#ActionNode)
-   [func (a \*ActionNode) Copy() Node](#ActionNode.Copy)
-   [func (a \*ActionNode) String() string](#ActionNode.String)
-   [type BoolNode](#BoolNode)
-   [func (b \*BoolNode) Copy() Node](#BoolNode.Copy)
-   [func (b \*BoolNode) String() string](#BoolNode.String)
-   [type BranchNode](#BranchNode)
-   [func (b \*BranchNode) Copy() Node](#BranchNode.Copy)
-   [func (b \*BranchNode) String() string](#BranchNode.String)
-   [type BreakNode](#BreakNode)
-   [func (b \*BreakNode) Copy() Node](#BreakNode.Copy)
-   [func (b \*BreakNode) String() string](#BreakNode.String)
-   [type ChainNode](#ChainNode)
-   [func (c \*ChainNode) Add(field string)](#ChainNode.Add)
-   [func (c \*ChainNode) Copy() Node](#ChainNode.Copy)
-   [func (c \*ChainNode) String() string](#ChainNode.String)
-   [type CommandNode](#CommandNode)
-   [func (c \*CommandNode) Copy() Node](#CommandNode.Copy)
-   [func (c \*CommandNode) String() string](#CommandNode.String)
-   [type CommentNode](#CommentNode)
-   [func (c \*CommentNode) Copy() Node](#CommentNode.Copy)
-   [func (c \*CommentNode) String() string](#CommentNode.String)
-   [type ContinueNode](#ContinueNode)
-   [func (c \*ContinueNode) Copy() Node](#ContinueNode.Copy)
-   [func (c \*ContinueNode) String() string](#ContinueNode.String)
-   [type DotNode](#DotNode)
-   [func (d \*DotNode) Copy() Node](#DotNode.Copy)
-   [func (d \*DotNode) String() string](#DotNode.String)
-   [func (d \*DotNode) Type() NodeType](#DotNode.Type)
-   [type FieldNode](#FieldNode)
-   [func (f \*FieldNode) Copy() Node](#FieldNode.Copy)
-   [func (f \*FieldNode) String() string](#FieldNode.String)
-   [type IdentifierNode](#IdentifierNode)
-   [func NewIdentifier(ident string) \*IdentifierNode](#NewIdentifier)
-   [func (i \*IdentifierNode) Copy() Node](#IdentifierNode.Copy)
-   [func (i \*IdentifierNode) SetPos(pos Pos)
    \*IdentifierNode](#IdentifierNode.SetPos)
-   [func (i \*IdentifierNode) SetTree(t \*Tree)
    \*IdentifierNode](#IdentifierNode.SetTree)
-   [func (i \*IdentifierNode) String() string](#IdentifierNode.String)
-   [type IfNode](#IfNode)
-   [func (i \*IfNode) Copy() Node](#IfNode.Copy)
-   [type ListNode](#ListNode)
-   [func (l \*ListNode) Copy() Node](#ListNode.Copy)
-   [func (l \*ListNode) CopyList() \*ListNode](#ListNode.CopyList)
-   [func (l \*ListNode) String() string](#ListNode.String)
-   [type Mode](#Mode)
-   [type NilNode](#NilNode)
-   [func (n \*NilNode) Copy() Node](#NilNode.Copy)
-   [func (n \*NilNode) String() string](#NilNode.String)
-   [func (n \*NilNode) Type() NodeType](#NilNode.Type)
-   [type Node](#Node)
-   [type NodeType](#NodeType)
-   [func (t NodeType) Type() NodeType](#NodeType.Type)
-   [type NumberNode](#NumberNode)
-   [func (n \*NumberNode) Copy() Node](#NumberNode.Copy)
-   [func (n \*NumberNode) String() string](#NumberNode.String)
-   [type PipeNode](#PipeNode)
-   [func (p \*PipeNode) Copy() Node](#PipeNode.Copy)
-   [func (p \*PipeNode) CopyPipe() \*PipeNode](#PipeNode.CopyPipe)
-   [func (p \*PipeNode) String() string](#PipeNode.String)
-   [type Pos](#Pos)
-   [func (p Pos) Position() Pos](#Pos.Position)
-   [type RangeNode](#RangeNode)
-   [func (r \*RangeNode) Copy() Node](#RangeNode.Copy)
-   [type StringNode](#StringNode)
-   [func (s \*StringNode) Copy() Node](#StringNode.Copy)
-   [func (s \*StringNode) String() string](#StringNode.String)
-   [type TemplateNode](#TemplateNode)
-   [func (t \*TemplateNode) Copy() Node](#TemplateNode.Copy)
-   [func (t \*TemplateNode) String() string](#TemplateNode.String)
-   [type TextNode](#TextNode)
-   [func (t \*TextNode) Copy() Node](#TextNode.Copy)
-   [func (t \*TextNode) String() string](#TextNode.String)
-   [type Tree](#Tree)
-   [func New(name string, funcs \...map\[string\]any) \*Tree](#New)
-   [func (t \*Tree) Copy() \*Tree](#Tree.Copy)
-   [func (t \*Tree) ErrorContext(n Node) (location, context
    string)](#Tree.ErrorContext)
-   [func (t \*Tree) Parse(text, leftDelim, rightDelim string, treeSet
    map\[string\]\*Tree, funcs \...map\[string\]any) (tree \*Tree, err
    error)](#Tree.Parse)
-   [type VariableNode](#VariableNode)
-   [func (v \*VariableNode) Copy() Node](#VariableNode.Copy)
-   [func (v \*VariableNode) String() string](#VariableNode.String)
-   [type WithNode](#WithNode)
-   [func (w \*WithNode) Copy() Node](#WithNode.Copy)

### Package files

lex.go node.go parse.go

func IsEmptyTree 
----------------

```go
func IsEmptyTree(n Node) bool
```

IsEmptyTree reports whether this tree (node) is empty of everything but
space or comments.

func Parse 
----------

```go
func Parse(name, text, leftDelim, rightDelim string, funcs ...map[string]any) (map[string]*Tree, error)
```

Parse returns a map from template name to parse.Tree, created by parsing
the templates described in the argument string. The top-level template
will be given the specified name. If an error is encountered, parsing
stops and an empty map is returned with the error.

type ActionNode 
---------------

ActionNode holds an action (something bounded by delimiters). Control
actions have their own nodes; ActionNode represents simple ones such as
field evaluations and parenthesized pipelines.

```go
type ActionNode struct {
    NodeType
    Pos

    Line int       // The line number in the input. Deprecated: Kept for compatibility.
    Pipe *PipeNode // The pipeline in the action.
    // contains filtered or unexported fields
}
```

### func (\*ActionNode) Copy 

```go
func (a *ActionNode) Copy() Node
```

### func (\*ActionNode) String 

```go
func (a *ActionNode) String() string
```

type BoolNode 
-------------

BoolNode holds a boolean constant.

```go
type BoolNode struct {
    NodeType
    Pos

    True bool // The value of the boolean constant.
    // contains filtered or unexported fields
}
```

### func (\*BoolNode) Copy 

```go
func (b *BoolNode) Copy() Node
```

### func (\*BoolNode) String 

```go
func (b *BoolNode) String() string
```

type BranchNode 
---------------

BranchNode is the common representation of if, range, and with.

```go
type BranchNode struct {
    NodeType
    Pos

    Line     int       // The line number in the input. Deprecated: Kept for compatibility.
    Pipe     *PipeNode // The pipeline to be evaluated.
    List     *ListNode // What to execute if the value is non-empty.
    ElseList *ListNode // What to execute if the value is empty (nil if absent).
    // contains filtered or unexported fields
}
```

### func (\*BranchNode) Copy 

```go
func (b *BranchNode) Copy() Node
```

### func (\*BranchNode) String 

```go
func (b *BranchNode) String() string
```

type BreakNode 
-----------------------------------------------

BreakNode represents a \{\{break\}\} action.

```go
type BreakNode struct {
    NodeType
    Pos
    Line int
    // contains filtered or unexported fields
}
```

### func (\*BreakNode) Copy 

```go
func (b *BreakNode) Copy() Node
```

### func (\*BreakNode) String 

```go
func (b *BreakNode) String() string
```

type ChainNode 
---------------------------------------------

ChainNode holds a term followed by a chain of field accesses (identifier
starting with \'.\'). The names may be chained (\'.x.y\'). The periods
are dropped from each ident.

```go
type ChainNode struct {
    NodeType
    Pos

    Node  Node
    Field []string // The identifiers in lexical order.
    // contains filtered or unexported fields
}
```

### func (\*ChainNode) Add 

```go
func (c *ChainNode) Add(field string)
```

Add adds the named field (which should start with a period) to the end
of the chain.

### func (\*ChainNode) Copy 

```go
func (c *ChainNode) Copy() Node
```

### func (\*ChainNode) String 

```go
func (c *ChainNode) String() string
```

type CommandNode 
----------------

CommandNode holds a command (a pipeline inside an evaluating action).

```go
type CommandNode struct {
    NodeType
    Pos

    Args []Node // Arguments in lexical order: Identifier, field, or constant.
    // contains filtered or unexported fields
}
```

### func (\*CommandNode) Copy 

```go
func (c *CommandNode) Copy() Node
```

### func (\*CommandNode) String 

```go
func (c *CommandNode) String() string
```

type CommentNode 
-------------------------------------------------

CommentNode holds a comment.

```go
type CommentNode struct {
    NodeType
    Pos

    Text string // Comment text.
    // contains filtered or unexported fields
}
```

### func (\*CommentNode) Copy 

```go
func (c *CommentNode) Copy() Node
```

### func (\*CommentNode) String 

```go
func (c *CommentNode) String() string
```

type ContinueNode 
--------------------------------------------------

ContinueNode represents a \{\{continue\}\} action.

```go
type ContinueNode struct {
    NodeType
    Pos
    Line int
    // contains filtered or unexported fields
}
```

### func (\*ContinueNode) Copy 

```go
func (c *ContinueNode) Copy() Node
```

### func (\*ContinueNode) String 

```go
func (c *ContinueNode) String() string
```

type DotNode 
------------

DotNode holds the special identifier \'.\'.

```go
type DotNode struct {
    NodeType
    Pos
    // contains filtered or unexported fields
}
```

### func (\*DotNode) Copy 

```go
func (d *DotNode) Copy() Node
```

### func (\*DotNode) String 

```go
func (d *DotNode) String() string
```

### func (\*DotNode) Type 

```go
func (d *DotNode) Type() NodeType
```

type FieldNode 
--------------

FieldNode holds a field (identifier starting with \'.\'). The names may
be chained (\'.x.y\'). The period is dropped from each ident.

```go
type FieldNode struct {
    NodeType
    Pos

    Ident []string // The identifiers in lexical order.
    // contains filtered or unexported fields
}
```

### func (\*FieldNode) Copy 

```go
func (f *FieldNode) Copy() Node
```

### func (\*FieldNode) String 

```go
func (f *FieldNode) String() string
```

type IdentifierNode 
-------------------

IdentifierNode holds an identifier.

```go
type IdentifierNode struct {
    NodeType
    Pos

    Ident string // The identifier's name.
    // contains filtered or unexported fields
}
```

### func NewIdentifier 

```go
func NewIdentifier(ident string) *IdentifierNode
```

NewIdentifier returns a new IdentifierNode with the given identifier
name.

### func (\*IdentifierNode) Copy 

```go
func (i *IdentifierNode) Copy() Node
```

### func (\*IdentifierNode) SetPos 

```go
func (i *IdentifierNode) SetPos(pos Pos) *IdentifierNode
```

SetPos sets the position. NewIdentifier is a public method so we can\'t
modify its signature. Chained for convenience. TODO: fix one day?

### func (\*IdentifierNode) SetTree 

```go
func (i *IdentifierNode) SetTree(t *Tree) *IdentifierNode
```

SetTree sets the parent tree for the node. NewIdentifier is a public
method so we can\'t modify its signature. Chained for convenience. TODO:
fix one day?

### func (\*IdentifierNode) String 

```go
func (i *IdentifierNode) String() string
```

type IfNode 
-----------

IfNode represents an \{\{if\}\} action and its commands.

```go
type IfNode struct {
    BranchNode
}
```

### func (\*IfNode) Copy 

```go
func (i *IfNode) Copy() Node
```

type ListNode 
-------------

ListNode holds a sequence of nodes.

```go
type ListNode struct {
    NodeType
    Pos

    Nodes []Node // The element nodes in lexical order.
    // contains filtered or unexported fields
}
```

### func (\*ListNode) Copy 

```go
func (l *ListNode) Copy() Node
```

### func (\*ListNode) CopyList 

```go
func (l *ListNode) CopyList() *ListNode
```

### func (\*ListNode) String 

```go
func (l *ListNode) String() string
```

type Mode 
------------------------------------------

A mode value is a set of flags (or 0). Modes control parser behavior.

```go
type Mode uint
```

```go
const (
    ParseComments Mode = 1 << iota // parse comments and add them to AST
    SkipFuncCheck                  // do not check that functions are defined
)
```

type NilNode 
-------------------------------------------

NilNode holds the special identifier \'nil\' representing an untyped nil
constant.

```go
type NilNode struct {
    NodeType
    Pos
    // contains filtered or unexported fields
}
```

### func (\*NilNode) Copy 

```go
func (n *NilNode) Copy() Node
```

### func (\*NilNode) String 

```go
func (n *NilNode) String() string
```

### func (\*NilNode) Type 

```go
func (n *NilNode) Type() NodeType
```

type Node 
---------

A Node is an element in the parse tree. The interface is trivial. The
interface contains an unexported method so that only types local to this
package can satisfy it.

```go
type Node interface {
    Type() NodeType
    String() string
    // Copy does a deep copy of the Node and all its components.
    // To avoid type assertions, some XxxNodes also have specialized
    // CopyXxx methods that return *XxxNode.
    Copy() Node
    Position() Pos // byte position of start of node in full original input string
    // contains filtered or unexported methods
}
```

type NodeType 
-------------

NodeType identifies the type of a parse tree node.

```go
type NodeType int
```

```go
const (
    NodeText    NodeType = iota // Plain text.
    NodeAction                  // A non-control action such as a field evaluation.
    NodeBool                    // A boolean constant.
    NodeChain                   // A sequence of field accesses.
    NodeCommand                 // An element of a pipeline.
    NodeDot                     // The cursor, dot.

    NodeField      // A field or method name.
    NodeIdentifier // An identifier; always a function name.
    NodeIf         // An if action.
    NodeList       // A list of Nodes.
    NodeNil        // An untyped nil constant.
    NodeNumber     // A numerical constant.
    NodePipe       // A pipeline of commands.
    NodeRange      // A range action.
    NodeString     // A string constant.
    NodeTemplate   // A template invocation action.
    NodeVariable   // A $ variable.
    NodeWith       // A with action.
    NodeComment    // A comment.
    NodeBreak      // A break action.
    NodeContinue   // A continue action.
)
```

### func (NodeType) Type 

```go
func (t NodeType) Type() NodeType
```

Type returns itself and provides an easy default implementation for
embedding in a Node. Embedded in all non-trivial Nodes.

type NumberNode 
---------------

NumberNode holds a number: signed or unsigned integer, float, or
complex. The value is parsed and stored under all the types that can
represent the value. This simulates in a small amount of code the
behavior of Go\'s ideal constants.

```go
type NumberNode struct {
    NodeType
    Pos

    IsInt      bool       // Number has an integral value.
    IsUint     bool       // Number has an unsigned integral value.
    IsFloat    bool       // Number has a floating-point value.
    IsComplex  bool       // Number is complex.
    Int64      int64      // The signed integer value.
    Uint64     uint64     // The unsigned integer value.
    Float64    float64    // The floating-point value.
    Complex128 complex128 // The complex value.
    Text       string     // The original textual representation from the input.
    // contains filtered or unexported fields
}
```

### func (\*NumberNode) Copy 

```go
func (n *NumberNode) Copy() Node
```

### func (\*NumberNode) String 

```go
func (n *NumberNode) String() string
```

type PipeNode 
-------------

PipeNode holds a pipeline with optional declaration

```go
type PipeNode struct {
    NodeType
    Pos

    Line     int             // The line number in the input. Deprecated: Kept for compatibility.
    IsAssign bool            // The variables are being assigned, not declared; added in Go 1.11
    Decl     []*VariableNode // Variables in lexical order.
    Cmds     []*CommandNode  // The commands in lexical order.
    // contains filtered or unexported fields
}
```

### func (\*PipeNode) Copy 

```go
func (p *PipeNode) Copy() Node
```

### func (\*PipeNode) CopyPipe 

```go
func (p *PipeNode) CopyPipe() *PipeNode
```

### func (\*PipeNode) String 

```go
func (p *PipeNode) String() string
```

type Pos 
---------------------------------------

Pos represents a byte position in the original input text from which
this template was parsed.

```go
type Pos int
```

### func (Pos) Position 

```go
func (p Pos) Position() Pos
```

type RangeNode 
--------------

RangeNode represents a \{\{range\}\} action and its commands.

```go
type RangeNode struct {
    BranchNode
}
```

### func (\*RangeNode) Copy 

```go
func (r *RangeNode) Copy() Node
```

type StringNode 
---------------

StringNode holds a string constant. The value has been \"unquoted\".

```go
type StringNode struct {
    NodeType
    Pos

    Quoted string // The original text of the string, with quotes.
    Text   string // The string, after quote processing.
    // contains filtered or unexported fields
}
```

### func (\*StringNode) Copy 

```go
func (s *StringNode) Copy() Node
```

### func (\*StringNode) String 

```go
func (s *StringNode) String() string
```

type TemplateNode 
-----------------

TemplateNode represents a \{\{template\}\} action.

```go
type TemplateNode struct {
    NodeType
    Pos

    Line int       // The line number in the input. Deprecated: Kept for compatibility.
    Name string    // The name of the template (unquoted).
    Pipe *PipeNode // The command to evaluate as dot for the template.
    // contains filtered or unexported fields
}
```

### func (\*TemplateNode) Copy 

```go
func (t *TemplateNode) Copy() Node
```

### func (\*TemplateNode) String 

```go
func (t *TemplateNode) String() string
```

type TextNode 
-------------

TextNode holds plain text.

```go
type TextNode struct {
    NodeType
    Pos

    Text []byte // The text; may span newlines.
    // contains filtered or unexported fields
}
```

### func (\*TextNode) Copy 

```go
func (t *TextNode) Copy() Node
```

### func (\*TextNode) String 

```go
func (t *TextNode) String() string
```

type Tree 
---------

Tree is the representation of a single parsed template.

```go
type Tree struct {
    Name      string    // name of the template represented by the tree.
    ParseName string    // name of the top-level template during parsing, for error messages; added in Go 1.1
    Root      *ListNode // top-level root of the tree.
    Mode      Mode      // parsing mode; added in Go 1.16
    // contains filtered or unexported fields
}
```

### func New 

```go
func New(name string, funcs ...map[string]any) *Tree
```

New allocates a new parse tree with the given name.

### func (\*Tree) Copy 

```go
func (t *Tree) Copy() *Tree
```

Copy returns a copy of the Tree. Any parsing state is discarded.

### func (\*Tree) ErrorContext 

```go
func (t *Tree) ErrorContext(n Node) (location, context string)
```

ErrorContext returns a textual representation of the location of the
node in the input text. The receiver is only used when the node does not
have a pointer to the tree inside, which can occur in old code.

### func (\*Tree) Parse 

```go
func (t *Tree) Parse(text, leftDelim, rightDelim string, treeSet map[string]*Tree, funcs ...map[string]any) (tree *Tree, err error)
```

Parse parses the template definition string to construct a
representation of the template for execution. If either action delimiter
string is empty, the default (\"\{\{\" or \"\}\}\") is used. Embedded
template definitions are added to the treeSet map.

type VariableNode 
-----------------

VariableNode holds a list of variable names, possibly with chained field
accesses. The dollar sign is part of the (first) name.

```go
type VariableNode struct {
    NodeType
    Pos

    Ident []string // Variable name and fields in lexical order.
    // contains filtered or unexported fields
}
```

### func (\*VariableNode) Copy 

```go
func (v *VariableNode) Copy() Node
```

### func (\*VariableNode) String 

```go
func (v *VariableNode) String() string
```

type WithNode 
-------------

WithNode represents a \{\{with\}\} action and its commands.

```go
type WithNode struct {
    BranchNode
}
```

### func (\*WithNode) Copy 

```go
func (w *WithNode) Copy() Node
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/text/template/parse/>

