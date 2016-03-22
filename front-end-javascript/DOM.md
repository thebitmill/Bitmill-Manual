# DOM

HTML is turned into Document Object Model. It's a very simple, but
quite powerful concept.

Essentially all XML tags in the HTML are rendered into a tree of Nodes. These Nodes all have one
parent and can have siblings and children. The highest level Node is the
`<html>`, and is reached from `document.documentElement`.  The `<html>` parent
is an instance of `Document`, which itself is a `Node` (`Document` inherits from `Node`), but
does not have a parent. The `<body>` is reachable from `document.body`.

Most nodes are `Element`s (the tags) or `Nodes` (text nodes).
