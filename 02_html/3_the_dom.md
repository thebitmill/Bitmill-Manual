# The DOM

HTML is the language used to structure web pages, but HTML is internally
represented by the DOM (the Document Object Model) in web browers.
Most of the reasoning behind this is to facilitate
JavaScript to interaction with HTML.

HTML is turned into Document Object Model. It's a very simple, but
quite powerful concept.

The DOM is simply a hierarchal tree of all Nodes in a website. A single node is
represented by a [Node](https://developer.mozilla.org/en-US/docs/Web/API/Node)
instance, and multiple nodes are often represented by
[NodeLists](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
(CAUTION: NodeList's are Array like, but not )

## HTML > DOM

Essentially all XML tags in the HTML are rendered into a tree of Nodes. These
Nodes all have one parent and can have siblings and children. The highest level
Node is the `<html>`, and is reached from `document.documentElement`.  The
`<html>` parent is an instance of `Document`, which itself is a `Node`
(`Document` inherits from `Node`), but does not have a parent. The `<body>` is
reachable from `document.body`.

Most nodes are `Element`s (the tags) or `Nodes` (text nodes).

In a browser, each XML node of the HTML is represented as a single Node. The
root element of all webpages is the <html> tag, is known as the Document
Element and is referenced by the `document.documentElement`.  All nodes beside
the document element have one single parent, but can have multiple children. A
NodeList of all child nodes are referenced by the `node.childNodes`
(<https://developer.mozilla.org/en-US/docs/Web/API/Node/childNodes>) property.

The DOM is both hated and loved, and has historically been the source of
much headache; mainly due to inconsistencies in implementation between browsers.
The standardization process has finally matured and been adopted enough for the DOMto become 
a powerful tool in developing websites.


```html
<div>
  <h1><span>Test</span></h1>
  <p>Lorem shitsum.</p>
</div>
```

- Element (div)
  - Element (h1)
    - Element (span)
      - Text Node ('Test')
  - Element (p)
    - Text Node ('Lorem shitsum')

```html
<!doctype html>
<html>
  <body>
    <div>
      <h1><span>Test</span></h1>
      <p>Lorem shitsum.</p>
    </div>
  </body>
</html>
```

- Document
  - Element (html, `document.documentElement`)
    - Element (body, `document.body`)
      - Element (div)
        - Element (h1)
          - Element (span)
            - Text Node ('Test')
        - Element (p)
          - Text Node ('Lorem shitsum')


## Nodes

There are several types of nodes, the two most common being Text Nodes and
Element Nodes.

From MDN:

The following interfaces all inherit from Node its methods and properties:
Document, Element, CharacterData (which Text, Comment, and CDATASection
inherit), ProcessingInstruction, DocumentFragment, DocumentType, Notation,
Entity, EntityReference

`nodeType === 1` for Elements, and `node.nodeType === 3` for text nodes.

Each of instance of a Node, is just that, an instance. Just like all JavaScript
objects, new properties and methods can be assigned.

```
element.customData = 'poo';

console.log(element.customData);


element.dataset.test = 'poop';

// <div data-test="poop"><div>
```


## NodeLists

NodeLists can be live, or not live. A live node list reflects the
current state of the DOM. If an element is removed from the DOM, it is removed
from any live NodeList that contains it.

The only way to know which lists are live
and which are not,  you need to know which native nodelists in are live or not.

Live Nodelists:

1. `node.childNodes`

(Live) HTMLCollections:

1. `document.getElementByTagName()` & `element.getElementByTagName()`
2. `document.getElementByClassList()` & `element.getElementByClassList()`
3. `node.children`
