### The DOM and Developer Tools
* 
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

### CSS Selectors
* Element interfaces
  * Different elements support different properties. These properties are just objects; key-value pairs where you can reassign the values to change the node.
  * You can look up the element in the prototype chain to know what methods are available to each node (or the constructor)

### BOM
* Everything that has to do with the Browser that's not related exactly to the DOM. The things that we can access about the Browser in our code
* Whenever we type window in the console, it returns everything that we can do in the Browser as well as everything that we can do in the DOM
* Examples:
  * `console` object
  * `navigator` object
    * Gives us information about the Browser
  * `location` object
  * `history` object
    * history.back()
    * history.forward()
  * `localStorage` object
    * localStorage.setItem("weather", "wet")
    * localStorage takes a key and a value, kind of like a session
  * timers
    * setTimeOut(function(){console.log('hey brooke!')}, 1000) and setInterval

### Selecting DOM Nodes (//Read)
* Traversing the DOM
  * Selectors are part of the element class; we can use them on any element
  * Usually will be seen with a document prefix; however can select other elements as well
  * Examples:
    * document.getElementById('unique-element')
    * document.getElementsByClassName('many-elements')
    * document.getElementByQuerySelector('#unique-element')
    * document.getElementsByQuerySelectorAll('.many-elements')
    * document.getElementByTagName('p')
    * can combine selectors to retrieve siblings, can also chain selectors
* When a traversal, or a query returns a group of elements it is called an HTML collection. It does *not* return an array. HTML collections cannot be mapped over, it has no iterators built on top of it.
* To convert to an array-like structure use Array.prototype

### Modifying DOM Notes (//Update and Destroy)
* let element = document.querySelector('body')
* element.style.backgroundColor = 'pink'
* innerText and textContent vs. innerHTML
  * innerText = 'string': sets the inner text of a node
  * innerHTML = '<h2>string</h2>': sets the inner HTML of a node
  * document.createTextNode('string'): creates a text node that you can append to another element
* Append v. appendChild
  * Append = newer; less buggy
* removing Elements

### Creating DOM Nodes (//Create)
* const h2 = document.createElement('h2')
* body.append(h2)

### Templating
* An outline for how things should look, in Ruby/Rails we used ERB tags
* With JavaScript, we are able to define a template and pass it different types of information
* Now we'll write templates for dynamically updating our web page without refreshing

<!-- ### Destructuring, in Johann's lecture he took a side bar to explain ES6 destructing, do you think it's worth covering  -->
