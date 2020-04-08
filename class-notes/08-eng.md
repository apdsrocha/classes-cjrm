# DOM - Document Object Model

> DOM is created by the browser - it is not part of the language itself. When the HTML document is loaded into the browser, the DOM is created so that we can interact with HTML through JavaScript (add or remove items from the page, for example). Once the HTML is loaded, the browser creates an object that models that document called `document`. It contains several properties and methods that allow you to interact with the HTML document loaded in the browser.

The DOM describes the HTML page in a hierarchical tree format - a tree of `nodes`. Each element is known as a `node` (distinguished by elements such as title, h1 and p that contain` text nodes` within them).

 
![alt text](../img/dom-tree.png "Graph with representation of DOM tree with main root node (HTML), element nodes (title, div, h1, p) and text nodes")
