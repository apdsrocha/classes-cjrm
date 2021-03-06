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


## Getting and setting attributes

We can select and change attributes of HTML tags using `getAttribute` and` setAttribute`.

```
//EXAMPLE 1

const link = document.querySelector('a')
// get reference to 'p' tag

link.getAttribute('href');
// get only the value of the 'href' attribute

link.setAttribute('href', 'https://google.com')
// two arguments: the attribute we want to change and the value we want to change to.


// EXAMPLE 2

const paragraph = document.querySelector('p')
// get reference to 'p' tag

paragrah.setAttribute('class', 'success')
// change the paragraph class to 'sucess'
// if the attribute does not exist, it will be created

```



## Modifying in-line styles

It is possible to use `setAttribute` to make style changes, but keep in mind that they are overwritten. One way to include style changes without overwriting is to use the `style` property.

```
const title = document.querySelector('h1')
// get h1 reference

title.style.margin = '50px'
// changes the margin to 50 pixels

title.style.fontSize = '48px'
// changes the font size, remembering that we need to write in 'camel case'

title.style.margin = ''
// removes the margin property
```

When we want to manipulate style in-line we can use the `style` property. But most of the time it is more efficient to write CSS rules in a style sheet and manipulate the classes of the elements.




## Getting, adding, removing and toggling CSS classes


Through the `classList` property, we can access a` DOMTokenList` (an object similar to an array) that shows us the list of classes of an element. We can also chain together methods that allow us to make modifications:
```
const paragraph = document.querySelector('p')
// get reference from the 'p' tag

paragraph.classList.add('error')
// adds class 'error' to element 'p'

paragraph.classList.remove('error')
// removes the 'error' class from the 'p' element
```

To add a class if the element doesn't already have it, or remove if it does have it we can use `toggle`:
```
title = document.querySelector('h1')
// get the 'h1' tag reference

title.classList.toggle('test')
// remove or add the class 'test'
```





## Parents, children and siblings

> In the DOM tree it is possible to use different types of relationships (parents; children; siblings) to traverse the DOM between different elements and obtain larger selections of elements.


![alt text](../img/dom-relationships.png "Graphic scheme with representation of the DOM tree with its root node (HTML) and signaling hierarchy between parents / children and siblings.")


When we need to obtain the reference of several elements within a tag (or if they are dynamic and we are not sure how many elements we want to search for within a tag) we can select the "parent" tag and obtain the reference of all its "children" by making use of the `children` property.
```
const article = document.querySelector('article')
// get reference of the 'article' tag

article.children 
// HTML Collection with all elements that are inside the article (does not allow iterating with forEach)

Array.from(article.children)
// Array with all elements that are inside the 'article' tag (we can now use Array methods)
```

We can also obtain the reference of an element and discover the element 'parent' (which is directly above in the DOM tree).
```
const title = document.querySelector('h2')
// get reference of the 'h2' tag

title.parentElement
// we managed to get the parent of the title element

title.parentElement.parentElement
// you can chain methods together and find the element above the parent.
```


To discover the sibling elements:
```
title.nextElementSibling
// following tag

title.previousElementSibling
// previous tag (returns `null` if it does not exist)
```
