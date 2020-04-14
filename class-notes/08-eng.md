# DOM - Document Object Model

> DOM is created by the browser - it is not part of the language itself. When the HTML document is loaded into the browser, the DOM is created so that we can interact with HTML through JavaScript (add or remove items from the page, for example). Once the HTML is loaded, the browser creates an object that models that document called `document`. It contains several properties and methods that allow you to interact with the HTML document loaded in the browser.

The DOM describes the HTML page in a hierarchical tree format - a tree of `nodes`. Each element is known as a `node` (distinguished by elements such as title, h1 and p that contain` text nodes` within them).

 
![alt text](../img/dom-tree.png "Graph with representation of DOM tree with main root node (HTML), element nodes (title, div, h1, p) and text nodes")



## Query Selector & Query Selector All

When we add, remove or modify content on the page, we need to decide which element of the page to manipulate and then look for that element in the DOM. 

To search for this reference (the node of the searched element) we can use some methods.

Example storing a tag or selector reference in a variable:
```
const paragraph = document.querySelector('p')
// selects the first p tag found.

const divError = document.querySelector('div.error')
// selects the first div with error class.
```

To search for multiple elements we can use the `querySelectorAll`, which runs through the DOM, stores all references with the pointed tag / selector, returning a Node List.
```
const errors = document.querySelectorAll ('.error')
// returns a node list with all the elements in the document that have the error class.

console.log(errors)
// Node List(2) [p.error, div.error]
```

The Node List (a collection of nodes) is similar to an array (it even allows using some array methods) but it is not an array.

[Here is more information on Node Lists and a listing of properties and methods.](https://developer.mozilla.org/en-US/docs/Web/API/NodeList).


## Other ways to make queries in the DOM

An alternative to obtain the reference of an element is to use the `id` of a tag by using the method `getElementByID`
```
const title = document.getElementByID('title')
```

Likewise, we can use the class-specific method via `getElementsByClassName` which returns an HTML Collection.
```
const title = document.getElementsByClassName('title')
```

An HTML Collection is similar to a Node List, but more limited; [you can read more about it here](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection).

**It is preferable to use `querySelector` and` querySelectorAll` as they are more flexible. In addition to accepting CSS selectors and queries for any required elements, they also return a Node List (less limited than HTML Collections).**

## Modifying text and HTML elements

>After selecting an element in the DOM and obtaining its reference, it is possible to use properties to change it.

```
const paragraph = document.querySelector('p')
// selecting the p element

paragraph.innerText = 'Texto substituto'
// changing the text inside the p tag overwriting what is already there

paragraph.innerText += 'Texto adicionado'
// adding to the text that was already present
```

It is also possible to change the HTML within an element.
```
const div = document.querySelector('.content')
// selecting an element

div.innerHTML = '<h2>Novo h2</h2'>
// tag inserted into the div overwriting what was already there.

div.innerHTML += '<h2>Novo h2</h2'>
// tag added keeping what was already inside the div.
```

The `innerText` and` innerHTML` properties are **getters and setters**, which means that they can **get and set values**.