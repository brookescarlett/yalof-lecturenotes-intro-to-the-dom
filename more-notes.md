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



  * You write code that interacts with Browser APIs: Collection of methods that you can call on. Defined, standardized way to interact with the DOM. Everything that's given to us by the document is given to us by the DOM API.
  * Code written adhering to JS Standard Library
  * Code compiled by a JS Engine (Chrome uses v8)
  * Browser turns strings into objects, converts to Browser code

  
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
    * document.QuerySelector('#unique-element')
    * document.QuerySelectorAll('.many-elements')
      * Returns a node list, instead of an HTML collection. That has an iterator available.
    * document.getElementByTagName('p')
    * can combine selectors to retrieve siblings, can also chain selectors
* When a traversal, or a query returns a group of elements it is called an HTML collection. It does *not* return an array. HTML collections cannot be mapped over, it has no iterators built on top of it.
* To convert to an array-like structure use Array.prototype

### Modifying DOM Notes (//Update and Destroy)
* let element = document.querySelector('body')
* element.style.backgroundColor = 'pink'
* innerText and textContent vs. innerHTML
  * innerText = 'string': sets the inner text of a node
  * innerHTML = ``<h2>string</h2>``: sets the inner HTML of a node
  * document.createTextNode('string'): creates a text node that you can append to another element
* Append v. appendChild
  * Append = newer; less buggy
  * Append gives us more freedom in terms of what we can pass through, but is not implemented by all browsers yet
* removing Elements

### Creating DOM Nodes (//Create)
* document.createElement creates a HTML Element, which has the properties available to it like every other node on the page
* const h2 = document.createElement('h2')
* body.append(h2)

### Templating
* An outline for how things should look, in Ruby/Rails we used ERB tags
* With JavaScript, we are able to define a template and pass it different types of information
* Now we'll write templates for dynamically updating our web page without refreshing

### Event Listeners
* Examples: DOMContentLoaded, onClick, onChange
* document.addEventListener(typeOfEvent, function(e){})

<!-- ### Destructuring, in Johann's lecture he took a side bar to explain ES6 destructing, do you think it's worth covering  -->


### Organizational Notes
* DOM is a collection of objects, shaped like a tree. Pull up a web page, play around with the DOM
* HTML is the structure of the page, the building blocks
* When we are sending HTML to a browser, passing information as strings.
* Browser converts strings into object.
* Engine underneath browser that turns strings into code (each browser has a different engine)
* JS Standard library, every browser has a slightly different implementation
* APIs: Describes how you interact with an application, that you can call things, defined way to interact with it
* Browser has an API, defines how you can interact with the browser
* Every element is a node, and they are all related (cousins, or brothers and sisters)
* Find them by traversing the DOM
* Elements can be manipulated
  * Look at HTML
  * Where does the title show up?
  * How do I grab the container?
  * Go through each of the ways to get an element.
* Create an element  
  * Append to page
  * Give it styles
  * Remove from page
* Single Page Applications: don't need to press refresh, if I want to go from showing a user one page to the next, you just change what you display on page using dynamic JS methods
  * Don't need to refresh to see the next page, to get more information


## Lecture Plan :
1. Open up index.html, ask students what's the DOM
2. Show page source; this is what is sent over the wire, over the internet to our Browser. Once this get's to our Browser the magic happens. The Browser reads it and converts it to the DOM.
3. DOM can be seen inside of the 'Elements' tab of the developer tools. Everything there is not what we've written, not what we've sent across the wire, but how our code has been interpreted by the Browser. This is a visual representation of the DOM. This shows what's on our page currently.
4. DOM stands for Document Object Model. When it's sent across the wire, the browser will read the string and convert all of the tags into JS objects (there's a constructor for each one of the tags)
5. Each one of the HTML tags converted into objects and then given to us as a property of the document object. Document object is the property that we'll use to do all of our DOM manipulation
6. What's the structure of the DOM?
7. Select the document; show that it has children; change the backgroundColor of a child... do this all through console.dir(NODE)
8. Okay, but there's a much more straightforward way to do that (go through all the ways of selecting)

9. HOW THIS ALL WORKS:
* How does JavaScript work in the browser?
  * Code for the browser written in C/C++ or some low level language
  * On top of that, we have the JS engine. Also written in a low level language, and this is what supports our ability to use JS. The browser itself does not know how to interpret JS, this is an add-on to the browser. (Chrome uses a v8 engine)
  * Many browsers have different engines, but v8 is shared across a few. Each engine has it's own implementation, meaning that each engine supports its own type of JS. So there's not one type, there are many interpretations.
  * Engine tells us what is included in the JS standard library. Anything that we can do in JS is given to us in this standard library.
  * On top of that, we have Browser APIs. The collection of methods that you can call on an array is an API for that array. Here, we are using the DOM API. That means that everything that's given to us by this document is given to us by the DOM API.
  * API: defined way to interact with something. We are used to using web apis, a website that we can interact with: defined set of websites and URLs that we can interact with. This is a defined way to interact with the document. Example: when we are defining a class and its methods, we are defining an API for that class.  
