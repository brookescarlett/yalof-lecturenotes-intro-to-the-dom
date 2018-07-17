## The DOM & The BOM

### The DOM and Developer Tools
* What is the DOM?
  * Document Object Model
  * Object-oriented representation of the webpage, which allows programs to manipulate the properties and contents on a page  
  * When HTML is compiled (done through an engine that is unique to every browser), the DOM is created based on that HTML
    * You write code that interacts with Browser APIs: Collection of methods that you can call on. Defined, standardized way to interact with the DOM. Everything that's given to us by the document is given to us by the DOM API.
    * Code written adhering to JS Standard Library
    * Code compiled by a JS Engine (Chrome uses v8)
    * Browser turns strings into objects, converts to Browser code
  * Javascript is a language created to manipulate the DOM

* What's the structure of the DOM?
  * An upside-down tree; where the root is the Document
  * Every node on the tree (except the root) has parent and child elements
  * These are all objects *related* to one another
  * Each of these nodes has properties that can be manipulated

### BOM
* Everything that has to do with the Browser that's not related exactly to the DOM. The things that we can access about the Browser in our code
* Whenever we type window in the console, it returns everything that we can do in the Browser as well as everything that we can do in the DOM
* Examples:
  * `console` object
  * `navigator` object
  * `location` object
  * `history` object
  * `localStorage` object
  * timers

### CSS Selectors
* Element interfaces
  * Different elements support different properties. These properties are just objects; key-value pairs where you can reassign the values to change the node.
  * You can look up the element in the prototype chain to know what methods are available to each node (or the constructor)
    * `_proto_`

### Read
* Traversing the DOM
  * Selectors are part of the element class; we can use them on any element
  * Usually will be seen with a document prefix; however can select other elements as well
  * Examples:
    * document.getElementById('unique-element')
    * document.getElementsByClassName('many-elements')
    * document.querySelector('#unique-element')
    * document.querySelectorAll('.many-elements')
      * Returns a node list, instead of an HTML collection. That has an iterator available.
    * document.getElementByTagName('p')
  * Note: you can combine selectors to retrieve siblings, can also chain selectors
* Unless you are using ```querySelectorAll```, when an HTML traversal returns a group of elements it is called an HTML collection. It does *not* return an array. This datatype cannot be mapped over like a typical array; however, they can be coerced into Arrays.
  * Array.prototype[...]

### Update
* There are many ways to update nodes on the DOM, and many properties that you can update
* innerText and textContent vs. innerHTML
  * innerText = 'string': sets the inner text of a node
  * innerHTML = ``<h2>string</h2>``: sets the inner HTML of a node
    * When using innerHTML +=, you overwrite existing event listeners
  * document.createTextNode('string'): creates a text node that you can append to another element
* Append v. appendChild
  * Append = newer; less buggy
  * Append gives us more freedom in terms of what we can pass through, but is not implemented by all browsers yet

### Create
* Create an element on the DOM with document.createElement('p')
* Then, give the new element some properties
* Finally, append the element to the DOM

### Delete
* Can remove elements from the DOM in many ways; most common is to select the parent and call .removeChild()

### Templating
* An outline for how things should look, in Ruby/Rails we used ERB tags
* With JavaScript, we are able to define a template and pass it different types of information
* Now we'll write templates for dynamically updating our web page without refreshing

### Activity
* Go to your favorite website and modify the DOM programmatically. Wikipedia and Twitter are good examples.
* Tasks:
  * Select elements and save them to variables
  * Delete at least 2 elements
  * Modify elements (e.g., replace image url, change text, change CSS)
  * Create new elements and add to page
  * Encourage students to think programmatically about the DOM by giving them problems that involve iteration and the use of multiple CSS selectors
  * Change all instances of one word
  * Replace all images on only a certain portion of the DOM
  * Change every other header
  * Bonus (Hard): replace all elements of one tag to another (e.g., p to h1)
